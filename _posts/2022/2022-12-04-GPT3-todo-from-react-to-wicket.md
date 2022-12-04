---
layout: post
status: publish
published: true
title: "Rewrite a To Do App From React to Wicket Using GPT-3"
---
Open AI has opened up their GPT-3 playground and I was looking at what the
capabilities of this AI are. So I tried it with a couple of tasks and was
amazed.

So I found a ReactJS example application for registering to-do's and thought
"what would happen if I ask GPT-3 to rewrite the ReactJS code to Java Wicket?"

So this linked article shows the To Do application in React JS. I am no expert
in ReactJS, but it does seem small, to the point and looks like anyone could
muster in a couple of hours without any prior ReactJS knowledge.

So I fired up Open AI and asked it to rewrite the code to Wicket Java and HTML:

> Rewrite this reactjs application to Wicket ajax and HTML

And pasted in the completed To Do application source code. You can see it in 
action in this video I uploaded to my YouTube channel:

<iframe width="560" height="315" src="https://www.youtube.com/embed/lkRYN6TrO8s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

It is quite impressive to see the code getting written by the AI, and from a 
glance it shows code I would write on a white board myself. But does it compile
and work? Let's see!

The generated Java code:

```java
public class App extends WebPage {
    private static final long serialVersionUID = 1L;
    
    private List<Todo> todos = Arrays.asList(
        new Todo("This is a sample todo", false)
    );
    
    public App() {
        add(new Label("title", "Todo List"));
        add(new FormTodoForm("formTodoForm"));
        add(new ListView<Todo>("todos", todos) {
            @Override
            protected void populateItem(ListItem<Todo> item) {
                item.add(new TodoPanel("todo", item.getModel()));
            }
        });
    }
    
    private class FormTodoForm extends Form<Void> {
        private static final long serialVersionUID = 1L;
        
        private TextField<String> textField;
        
        public FormTodoForm(String id) {
            super(id);
            
            add(new Label("formTodoLabel", "Add Todo"));
            
            textField = new TextField<>("textField", Model.of(""));
            add(textField);
            
            add(new Button("submit") {
                @Override
                public void onSubmit() {
                    if (StringUtils.isNotBlank(textField.getValue())) {
                        todos.add(new Todo(textField.getValue(), false));
                        textField.setModelObject("");
                    }
                }
            });
        }
    }
    
    private class TodoPanel extends Panel {
        private static final long serialVersionUID = 1L;
        
        private Todo todo;
        
        public TodoPanel(String id, IModel<Todo> model) {
            super(id, model);
            this.todo = model.getObject();
            add(new Label("text", todo.getText()).setRenderBodyOnly(true));
            add(new AjaxLink<Void>("markTodo") {
                @Override
                public void onClick(AjaxRequestTarget target) {
                    todo.setDone(true);
                    target.add(TodoPanel.this);
                }
            });
            add(new AjaxLink<Void>("removeTodo") {
                @Override
                public void onClick(AjaxRequestTarget target) {
                    todos.remove(todo);
                    target.add(TodoPanel.this.getParent());
                }
            });
        }
        
        @Override
        protected void onConfigure() {
            super.onConfigure();
            addStateChange();
        }
    }
    
    private static class Todo implements Serializable {
        private static final long serialVersionUID = 1L;
        
        private String text;
        private boolean done;
        
        public Todo(String text, boolean done) {
            this.text = text;
            this.done = done;
        }
        
        public String getText() {
            return text;
        }
        
        public boolean isDone() {
            return done;
        }
        
        public void setDone(boolean done) {
            this.done = done;
        }
    }
}
```

And the generated HTML markup:

```html
<html xmlns:wicket="http://wicket.apache.org">
    <body>
            <h1 wicket:id="title" class="text-center mb-4"></h1>
            <form wicket:id="formTodoForm">
                <label wicket:id="formTodoLabel"><b>Add Todo</b></label>
                <input type="text" wicket:id="textField" class="input" placeholder="Add new todo" />
                <button wicket:id="submit" type="submit">Submit</button>
            </form>
            <div>
                <ul>
                    <li wicket:id="todos" class="todo">
                        <span wicket:id="text"></span>
                        <a wicket:id="markTodo" class="outline-success" href="#">✓</a>
                        <a wicket:id="removeTodo" class="outline-danger" href="#">✕</a>
                    </li>
                </ul>
            </div>
        </wicket:panel>
    </body>
</html>
```

First of all I need to generate a full Wicket application using the Quick Start 
generator found on the Wicket website. I opened the project using VS Code and
pasted in the generated Java and HTML code into the HelloWorld.java and 
HelloWorld.html files.

As GPT-3 named the class `App`, I had to rename the files to `App.java` and 
`App.html`. Next I needed to fix the imports. There remained one import that was
not resolvable. So I asked GPT-3 what dependencies were necessary and it 
responded with the following 3 dependencies:

- wicket-core
- commons-lang3
- some JavaFX library

The JavaFX library is not necessary, so I don't know how it decided to include
that. The commons-lang3 was used for `StringUtils.isNotBlank()`. Asking GPT-3
for the Maven dependency got me:

```
<dependency>
  <groupId>org.apache.commons</groupId>
  <artifactId>commons-lang3</artifactId>
  <version>3.9</version>
</dependency>
```

Pasting that into my project's Maven POM made it almost compile. Because I used
a standard QuickStart I needed to change the `WicketApplication#getHomePage()` 
to return `App.class`.

Next I needed to 

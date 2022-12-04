---
layout: post
status: draft
published: false
title: "Rewrite a To Do App From React to Wicket Using GPT-3"
---
_NB: This is a draft post, not finished yet_

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

## The Web Page's Constructor

GPT-3 generated the following web page and constructor:

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
```

The page has one field containing the todo items (the `Todo` class is defined 
later) and it initializes it with a list containing one todo item. Note that it
contains a `serialVersionUID`, saving us a compiler warning.

Each page will have a title, a form for adding a todo item and a listview 
displaying all todo items in a `TodoPanel`. GPT-3 has chosen to create custom
composite components for the form and the todo items.

### The FormTodoForm

Apart from the name `FormTodoForm`, which I find a bit too much repetitive, the
code structure is pretty ok:

```java
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
```

The composite component has a property for the `textField` and that is necessary
to reference it in the `onSubmit` of the button component (but not strictly 
necessary, because a local variable could be effectively final). GPT-3 adds a
label with the appropriate text, but that could've been included in the markup
without adding a component.

GPT-3 also adds a text field component, and initializes the model with an empty
string, again correctly. Finally a `Button` is added with an `onSubmit` handler
that validates the input to prevent an empty todo item from being added. It
correctly transfers the text of the todo item to the constructor of the `Todo`
class. And finally, when an item was added, it will reset the text field.

Thumbs up for the form component! Next up displaying the list of todo items.

### The TodoPanel

The AI also chose to create a Wicket panel component for each todo item in the
list of todos. While the structure of the code is correct, the implementation
would not work, as Wicket panel components need to have their own markup file.

It generated a constructor, a `Todo` field and an `onConfigure` method. The
`todo` field should for production ready code not be added in this way. It is
bad form to add (JPA) entities directly to your component tree, and you should
manage those through models. So the AI does have the right idea of passing the
todo item through an `IModel` parameter, but doesn't make particular good use
of this.

In the constructor a label for the todo text is added, and two AJAX links: one
for marking the todo item as done, and one for removing the todo item. The
event handlers are implemented correctly, even the removal of the todo item
seems to use the parent component of the just removed panel, which is the
`ListItem`. The intent seems there, but the implementation not. The rendered
list markup would not be updated as the todo panel is a child of a `ListView`
item that would no longer exist during a new rendering of the `ListView`
component: the todo item was removed and as such no corresponding `ListItem`
would be created.

The generated `onConfigure` method has no actual meaning in this instance, so
should not have been generated.

```java
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
```

Changing the parent to `WebMarkupContainer` would bring it one step closer to
actually working. The concept of `Fragment` could also be a possibility but the
generated markup seems to imply that the AI confused panels and 
web markup containers. 

The `todo` Wicket identifier is glaringly missing from the generated markup. 
This suggest that GPT-3 has mixed generating a page and a panel, and the 
definition and use of a Wicket panel.

```html
<html xmlns:wicket="http://wicket.apache.org">
    <body>
        <wicket:panel>
            [... snipped form markup ...]
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

In this case replacing the parent class of the `TodoPanel` with `WebMarkupContainer`
and fixing the markup by removing the `<wicket:panel>` tags, and adding a 
`<div wicket:id="todo">` as a child of the `<li wicket:id="todos">` is enough to
get this part to work.


### Setting up the project

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

---
layout: post
status: draft
published: false
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

And pasted in the completed To Do application source code.

You can see it in action in this video I uploaded to my YouTube channel:

<iframe width="560" height="315" src="https://www.youtube.com/embed/lkRYN6TrO8s" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

It is quite impressive to see the code getting written by the AI, and from a 
glance it shows code I would write on a white board myself. But does it compile
and work? Let's see!

First of all I need to generate a full Wicket application using the Quick Start 
generator found on the Wicket website. I opened the project using VS Code and
pasted in the generated Java and HTML code into the HelloWorld.java and 
HelloWorld.html files.

As GPT-3 named the class `App`, I had to rename the files to `App.java` and 
`App.html`. Next I needed to fix the imports. There remained one import that was
not resolvable. So I asked GPT-3 what dependencies were necessary and it 
responded with 

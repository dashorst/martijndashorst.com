---
layout: post
status: publish
published: true 
title: A Better HTML Autofocus Implementation
---

So you have this login form with a username and password field.
Typically you want the username to be pre-filled and the password to be empty for a password manager to fill or to type in.
It would be nice if the password field receives the focus  so you can start typing away and press <enter> to submit the login form.

But often the username field is also empty. And if that is the case, you want the userfield to have the focus.

Your first pick is to add the `autofocus` attribute to both fields:

```
<label for="username">Username:</label>
<input id="username" type="text" name="username" autofocus>

<label for="password">Password:</label>
<input id="password" type="password" name="password" autofocus>
```

But in some browsers this focuses the username field regardless of its contents, and in other browsers the password field is focussed, even though the username field is not filled.

It appears that the behavior of two fields with autofocus is not specified.

In one of my applications I solved this problem with a little JavaScript snippet that runs when the DOM is ready.

```
$('*:input:visible:enabled[value=\"\"]:eq(0)').first().focus()
```

This requires JQuery to be in your page, but if you want the Vanilla JS version, the line below will do the same:

```
document.querySelector('input[value=""]:enabled:not([style*="display: none"]):not([style*="display:none"]):first-child').focus()
```

This will filter the disabled, invisible, empty fields and select the first field to put the focus on.

If you are an Apache Wicket user, you can easily add this to your page using a _header item_, in particular the `OnDomReadyHeaderItem`, in the `renderHead()` method of your page.

Enjoy the best autofocus behavior you could wish for.
---
layout: default
---

# The Model View Controller pattern

The MVC (Model View Controller) pattern is popular in web apps. It lets you separate your concerns into the **Model** (the business logic), the **Controller** (the interaction logic), and the **View** (the UI (User Interface) logic).

![](/img/MVC.png)

**The Model handles the business logic**. It handles the data. It usually takes the form of a database.

**The Controller handles the interaction logic**. It process instructions and updates the Model and the View layers.

**The View handles the UI logic**. It handles what the user sees.

Often this is a "thin client": most things happen on the server. Some popular frameworks that work like that are Rails (Ruby), Django (Python), and Express (NodeJS). Some frameworks move more work to the client side (and are JavaScript-based), such Angular, Ember, and Backbone.

There are other kinds of pattern too, like MVVM (Model View ViewModel), MVP (Model View Presenter).

## I'm routing for you

Usually the MVC picture has a few more steps than the one above.

![](/img/MVC-with-router.png)

A request is made to a URL, like `/login`. This hits the applications Router. The Router then tells the Controller what to go and do. The Controller update the View and Model as it needs to, then sends the information to the Browser.

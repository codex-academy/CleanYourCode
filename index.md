---
layout: default
---

# Code cleanup and refactoring

You came a long way! You started off by processing a CSV file and displaying the data in a browser using a web server.  You created a data model using MySQL. Then you hooked the data model up to your web application to Create, Read, Update, and Delete data. Along the way you added a password and user roles. And don't forget the search support you added!

It's time now to stand back and review the code you wrote.

Where is most of your code? How do the different parts of the code relate to each other? You probably have a `server.js` or `index.js` file.  What modules did you import that contain code for products, sales, or purchases, for example? Do you have a monster `server.js` or `index.js` file that contains everything? **Take a quick look.**

## What's the prognosis?

How is it looking?

Any monolithic pieces of code (that is: big pieces that do a lot of things)? Or, even worse, one big piece of code that does everything?

If that is the case the first thing to do would be to split up your code up into smaller parts. Split up your code into modules that handle specific domains like products, sales, and categories. Decouple your code into logical components. This makes makes system maintenance much easier, and your code easier to understand.

One great way to improve your code is to do a Code Review with a partner. [Read more about CodeReviews](./steps/code_review.html) to learn more about how to do them, then find someone to sit with and review each other's code.


## Next steps

* Go and look at [refactoring](/steps/go_refactor.html).
* Make sure your [code is testable](/steps/refactor_to_be_testable.html).
* Look at Promises for [a better way to handle callbacks](/steps/promises.html).
* Refactor your [database modules to use Promises](/steps/refactor_to_using_promises.html)

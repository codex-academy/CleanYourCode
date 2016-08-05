---
layout: default
---

# Go refactor

<!--codex ignore maintain-->
Refactoring is the process of making your codebase better without changing its behaviour. It improves the way your code is written and it improves the structure. Refactoring makes it easier for future you and others to maintain and extend your code.

Go ahead refactor your code by:

* adding modules for Categories, Products, Sales, Purchases, and Suppliers;
* looking at your project web routes. Are they consistent? For example : `products/add`, `products/edit`, `products/update`, and `products/delete`. Whatever convention you are following, be consistent. Use lowercase for route names.
* ensuring that all `express` `get` and `post` handlers are in modules and you have no inline function calls.

This is not so good:

```javascript
app.get('/products', function(req, res){
    // lots of code here
});
```

This is better:

```javascript
app.get('/products', products.showProducts);
```

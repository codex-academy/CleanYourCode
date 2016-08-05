---
layout: default
---

# The future

Once your codebase is using Promises you can start using co-routines, if you are using using a version of Node that supports generators. Read [more about generators on promisejs.org](https://www.promisejs.org/generators/) or [on MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators#Generators). Co-routines are an elegant way of handling callbacks using generators.

Generators are a feature of [ES6/ES2015](https://babeljs.io/docs/learn-es2015/): the new version of JavaScript. Generators allow JavaScript code to block and are supported from [NodeJS 4.0 onwards](http://node.green).

You can install NodeJS 4.0 using [nvm](https://github.com/creationix/nvm), the Node Version Management utility.

To use co-routines look at the [co npm module](https://www.npmjs.com/package/co) or [bluebirds co-routine](http://bluebirdjs.com/docs/api/promise.coroutine.html) support.

This example using Promises

```javascript
userService
    .findAllUsers()
    .then(function(users){
        res.render('users', users);
    })
    .catch(function(err){
        next(err);
    });
```

can refactored to use co-routines using [co](https://www.npmjs.com/package/co) like this:

```javascript
co(function* (){
    try{
        var users = yield userService.findAllUsers();
        res.render('users', user)
    }
    catch(err){
        next(err);
    }
});
```

## Even cleaner database connections using Co-routines

Using the `connection-provider` module and co-routines together results in readable code. This almost doesn't look asynchronous, but be careful as it **is** still asynchronous code.

```javascript
exports.getProduct = function(req, res, next){

    co(function* (){
        var services = yield req.getServices();
        var productId = req.params.productId;
        var productsDataService = services.productDataService;
        var product = yield productsDataService.getProduct(productId);
        try{
            if (products && products.length > 0){
                res.render('product', {products : product});
            }
            else{
                res.render('product', {error : 'Product not found.'})
            }
        }
        catch(err){
            res.render('product', {error : err});
        }
    });

};
```

## Multiple callbacks

Co-routines makes calling multiple asynchronous methods easier.

Call multiple asynchronous methods like this:

```javascript
co(function* (){
    try{
        var users = userService.findAllUsers();
        var categories = userService.findAllCategories();

        var results = yield [users, categories];
        //[[user data], [category data]]
    }
    catch(err){
        next(err);
    }
});
```

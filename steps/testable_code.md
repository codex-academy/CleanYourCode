---
layout: default
---

# Testable code

You need to make sure that your code is tested. Your focus was on learning how to get things done, so we cheated a little. How much of your code are actually tested? Not much? Let's fix that!

You will need to decouple your code to make it testable. Decoupled code has different logical components that are separated out from each other.

Let's look at the code below:

```javascript
exports.getProduct = function(req, res, next){
        req.getConnection(function(err, connection){
            if (err) return next();
            var productId = req.params.productId;
            connection.query('select productName from products where productId = ?', productId, function(err, products){
                if (products && products.length > 0){
                    res.render('product', {products : product});
                }
                else{
                    res.render('product', {error : 'Product not found.'})
                }
            });
        });
};
```

Ask yourself:

* What is this code doing?
* How many reasons does this function have to change?
* How can I write a unit test to test it?

It's doing a lot, and it is hard to test! This code looks up things in the database, and shows something on the front-end depending on what the result is. It's concerned with both the back and front-end.

[Refactor to be testable](/steps/refactor_to_be_testable.html)

[Test database services using Travis](/steps/test_db_service_using_travis.html)

Now let's look at making [better database connections](better-database-connections.md).

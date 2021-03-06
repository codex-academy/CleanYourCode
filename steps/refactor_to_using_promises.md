---
layout: default
---

# Refactor to use Promises

We've now covered everything you need to know to refactor your database modules to use `Promises`. Replace any nested database callbacks with `join` function from `bluebird`.

A wrapper around the MySQL code like this will serve you well:

```javascript
var QueryBuilder = function(connection){
    this.execute = function(sql, params){
        return new Promise(function(resolve, reject) {
            connection.query(sql, params || {}, function(err, results) {
                if (err) return reject(err);
                resolve(results);
            });
        });
    }
}
```

Think about

* How would you use this wrapper?
* How would you handle nested database queries using bluebird's `join`?

You will need to instantiate one instance of the `QueryBuilder` when constructing instances of your database modules.

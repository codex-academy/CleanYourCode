---
layout: default
---
## Using a test database

Are you running your tests on Nelisa's database? What if your tests mess up some of Nelisa's data? Let's use a separate database instead, with an identical Schema and some sample data.

You'll need database scripts that can create and populate your database every time you run your tests. This is good practice and will ensure your database script and your database are synchronised.

Making sure that your unit tests have all the data they need to run is important. You will need to populate and cleanup your test database from mocha. Have a look at [Mocha's hooks](http://mochajs.org/#hooks) to run code before and after unit tests.

## Test database services with Travis

Now that you have Mocha tests for your database code, setup a Travis instance for your project. Look at [this example project](https://github.com/codex-academy/TravisWithDatabase) that uses Travis with a database. Note the `.travis.yml` especially.

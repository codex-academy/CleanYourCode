---
layout: default
---
## Test database services with Travis

Now that you have Mocha tests for your database code, setup a Travis instance for your project. You will need  database scripts that can create and populate your database every time Travis runs. This is a good practice and will ensure your database script and your database is synchronised.

Look at [example project](https://github.com/codex-academy/TravisWithDatabase) that use Travis with a database. Note the `.travis.yml` especially.

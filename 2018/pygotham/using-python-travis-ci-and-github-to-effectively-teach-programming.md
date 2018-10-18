# "Using Python, Travis CI, and GitHub to Effectively Teach Programming" by Gregory M. Kapfhammer

## Tools for development

* Black
* Flake8
* Pipenv
* Pylint
* Pytest and plugins


## Design principles

* Working code is not sufficient: aim for simplicity.
* Code that hasn't been executed doesn't work.
* Simple interfaces over simple implementations.
* Flexible checking-local or on GitHub via Travis CI.


## Build process

Travis CI runs private builds using Gradle plugin that can run Python checker with parallelism.

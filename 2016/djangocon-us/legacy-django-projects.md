# This Old Pony - Working with legacy Django projects
## Ben Lopatin

### Ideas

* `tox` creates matrices of test dependencies
* `pur` or `pip-tools` to evaluate and update reqs
* `autopep8`
* `bandit` looks for security vulnerabilities

### Legacy Software

* Code that has no tests
    * You don't know if you're improving it when you change it
* Code that's in production

### Issues

* Outdated versions
* Deployment issues
* No or few tests
* Older dependencies

### Assumptions

* Outdated Django version
* Code is in production

### Process

* Code review
* Orient, observe, decide, act (OODA)
* Gather understanding from outside the codebase
    * What's it supposed to do?
    * What does it actually do?
    * Known bugs
    * Planned features
* Read the code
    * Confusing areas
    * Architecture
    * Code smell
    * Style
* Static code analysis
    * flake8
    * PyCharm
    * pylint
* Add logging
* Generic `except` statements swallow bugs - log an exception there at the very least
* Silence bad tests while refactoring to lower signal:noise ratio
* Prioritize testing of bugs and new features
* Refactor
* Upgrade (minimally TLS)
* Fix outdated dependencies
* Remove secrets from settings
* Break up apps (urls.py and views.py to start, models.py later with migration tricks)
* Push logic from views and management commands to models, forms, helpers

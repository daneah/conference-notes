# "BDD Testing for Django Apps" by Le Xiao

## BDD environment setup

* `behave` library
* Gherkin feature files
* Selenium


### Tooling setup

1. Install chromedriver
1. Install geckodriver
1. Check if Selenium is able to launch a browser


### Testing setup

1. Create feature files
1. Apply a step convention:
  * Keywords translate to page objects and action words that formalize elements and behavior under test
1. Use fixtures for data, or use `factoryboy` to set up dummy data
1. Create a test runner to run all the features, scenarios, etc.


### Page objects

* Ask front-end development to create unique identifiers (whether `id` or custom `data-` attributes) for easier object identification


### Running tests

`python manage.py behave`


## Continuous integration/delivery

* Hiptest as a feature file management tool
* BrowserStack, SauceLabs, SmartBear for cross-platform testing
* PhantomJS or Puppeteer for headless browser testing

Minimizing test run time will cut down on cost for products that charge per-minute of execution time.


## Limitations

* Conditional testing is difficult since test descriptions are linear
* Selenium is sometimes difficult to use when interacting with JavaScript

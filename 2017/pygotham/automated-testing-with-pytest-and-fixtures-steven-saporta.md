# "Automated Testing with pytest and Fixtures" by Steven Saporta


### Features of pytest
* Assertion-based testing
  `pytest` tests validity of code through Python's built-in `assert` mechanisms, whereas `unittest` has its own
  conventions pulled from JUnit, the Java testing framework
* Simple test discovery
  Discovers tests via naming convention of directories, files, and methods
* Run tests by name match
  Run tests whose names match an expression
* Parallel testing with pytest-xdist
  Speed up your tests by running many at once. A pre-requisite is to make sure that tests are parallel-safe, i.e. don't
  manipulate the same data in ways that will make other tests fail since there's no guarantee of run order

### Fixtures

* Scope: run once per test, module, or session
  Fixtures have granular scope control that allow setup steps to be run on a per-test, per-module, or per-run basis
* Parameterize tests
  Allows running a test or set of tests with different inputs without having to duplicate code. Useful for something
  akin to fuzz testing or iterating over a sample of real data for sanity checking
* Do useful work like pre-verifying system state
  Can alter the working directory, create temporary or results directories, etc.
* Can create test records
  Really useful for performance when many tests will test some features of the same data record

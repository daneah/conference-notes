# "Next Level Testing Revisited" by [James Saryerwinnie](https://www.twitter.com/jsaryer), AWS


## Challenge
What kinds of testing can be done beyond unit and regression testing?


## Property-based testing

Generalize specific tests to test the desired behavior more realistically

Example: refactor multiple methods that test arbitrary integers into a single test that tests 50 random integers
on each run instead.


## State-based testing

Run some infrastructure setup steps and test the state of the system after each change

Example:

When creating a lambda, create resource should make API call to resource creation endpoint and deleting a function
in the uploaded code should delete the resource from the system instead of leaving it hanging, unused.


## Fuzz testing

Generate a random input and make sure the code does something sane, which could mean several things:
* Returning some default value
* Returning an empty value
* Erroring in an intentional way

Example use case:

Code has several independent logical branches and tests check all three (`100`, `010`, and `001`) but don't check
all permutations (such as `110` or `101`)
Captures issues that can arise outside of line/branch coverage

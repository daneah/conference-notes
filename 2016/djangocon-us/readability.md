# Readability
## Trey Hunner

### Ideas

* makes lives easier
* code is read more than written
* readability -> maintainability
* faster onboarding
* readability is not objective
* Document explicit styleguide beyond PEP-8
* name every variable with care
* Read code aloud to determine its descriptive nature

### Structuring Code

* line length is a human limitation, not a technical one
    * think about text width rather than line length for readability
    * short lines aren't the end goal!
* line breaks should be thoughtfully inserted
* parens get their own lines
* trailing commas

### Naming Things

* important concepts deserve names
* naming things is hard because describing things is hard
* long descriptive names are better than confusing short names
* use tuple unpacking over arbitrary variables when possible
* factor out named functions to replace pieces of code
* comments can mean the variable names are not descriptive enough

### The right tool for the right problem

* Sometimes context managers are suggested by the presence of "cleanup" steps
* Overload operators instead of using methods - `item in obj` vs. `obj.contains(item)`

### Questions

* Unneeded parens around right hand side – for readability?

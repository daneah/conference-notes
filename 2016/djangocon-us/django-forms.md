# Django Forms
## 

### Ideas


### What are Django forms?

* Structuring (contents)
* Rendering (presentation)
* Processing (validation)

### Dynamic Form Structure

* You could alter form structure/content in constructor, but that's unwieldy
    * OrderedDict of fields passed into constructor is better

* Using {% form %} tag helps
* Beware django-crispy-forms

* add\_error allows dynamic errors in validation step

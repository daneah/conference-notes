# Might Model Managers
## Shawn Inman, e-fellow

### Ideas

### Why are we here as software developers?

* For our users, business processes, for ourselves

### What are model managers?

* `Animal.objects.all()` is an example of using the `objects` manager
    * Can rename this default manager right in the model
* Control queryset returned
* Provide table-level functionality
* Customization

### Tasks

* Readability
* Encapsulation
* Manager subclass for specific querysets

### Drawbacks

* No custom code usable here
* A lot of subclasses

### QuerySet

* Subclass it! Then pass it to manager

### Django >= 1.7

* Tell it to extract the manager directly from the queryset using `.as_manager()`

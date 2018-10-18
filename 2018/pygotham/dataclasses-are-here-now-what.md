# "Dataclasses are here! Now what?" by Scott Irwin

Dataclasses are just normal Python classes, but intended as data containers.
They can be thought of like mutable `namedtuple`s with default values.
The module was added to the standard library in Python 3.7.


## Features

* `@dataclass` decorator signifies a class as a dataclass
* Optional values allow constructing a dataclass with no or partial initial inputs on instantiation
* Define arbitrary methods just like other classes
* Field types are just hints
* Access fields with dot syntax
* Methods added to dataclass by language: `__init__`, `__repr__`, `__eq__`
* _Ordered_ dataclasses also get `__lt__`, `__le__`, `__gt__`, `__ge__`
* Frozen dataclasses are immutable


## More complicated field structures

* Exclude it from `repr` or `init` or `compare`
* `default_factory` can be any callable that takes zero arguments.
  This helps avoid using mutable types as default arguments.


## Use cases

* Mutable data holder
* Want the comparison and other dunder methods without having to write boilerplate


## Non-use cases

* Python <3.7
* Need further features like value and type validation

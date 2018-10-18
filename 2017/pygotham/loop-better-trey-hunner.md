# "Loop Better" by [Trey Hunner](https://www.twitter.com/treyhunner)


Anything that can be subject to a `for` loop is an iterable, and anything that is iterable can be subjected to a `for` loop
Sequences are iterables that can be indexed numerically (lists, strings, etc.)

## for loops
Q: How can we loop over an iterable without using a for loop?
A1: You can use a while loop for sequences, but not for iterables in general
A2: Wrap iterables in an iterator (`iter`) and progress the iterator (`next()`)

```py
>>> iterator = iter([1, 2, 3, 4, 5])
>>> iterator
<list_iterator object a 0x7ab35>
>>> next(iterator)
1
```

## Notes about iterators
Iterators are unidirectional and get "used up" when you go through them
Iterators are iterables and are their own iterators
Iterators enable lazy evaluation; an item isn't evaluated until it's been iterated to
Iterators allow for infinitely long iterables (look at `itertools.count`)
You can produce generator-like behavior using the iterator protocol along with `yield`

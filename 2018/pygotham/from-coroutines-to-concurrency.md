# "From Coroutines to Concurrency" by Vishal Prasad

The global interpreter lock (GIL) is a mutex that prevents multiple bytecode instructions from executing simultaneously.
This doesn't tend to lose us much in practice, since we can scale infrastructure, use C extensions, and more to get around the performance limitation of single thread execution.

Coroutines were first raised by making `yield` an expression instead of a statement.
Pertinently, this allowed generators to not only produce values but receive them:

```python
def squared():
    while True:
        n = yield
        print(n ** 2)

sq = squared()
next(sq)
sq.send(1)
sq.send(2)
sq.send(3)
```

This makes cooperative multitasking possible but isn't quite concurrency.
Concurrency lets operations cede to each other when waiting on computation.


## Now

`asyncio` has replaced geneator-based coroutines.

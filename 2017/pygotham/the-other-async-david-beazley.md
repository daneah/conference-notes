# "The Other Async" by [David Beazley](https://www.twitter.com/dabeaz)

## Queues

* Queues will block and wait on `.get()` until there's something in the queue to read (maybe from another thread)
`concurrent.futures.Future` will wait for a future result
* Using a queue you can build in futures to promise the idea of a future `get` or `put`
* As operations are waiting to get or put an item, they will do so once that item arrives or space is available


## Rules of async

* Async functions don't run themselves; run inside an event loop until complete
* Async functions can call other async functions
* `await` can't be used outside async functions
* Don't talk about how it works
* `asyncio` loves nonblocking

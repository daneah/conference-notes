# "I've Been Awaiting for an URL Like You" by Brian Muller


## Distributed hash tables

Distributed hash tables (DHTs) provide a lookup, like a hash table, where any node in the network can look up values by key.


## IPFS

InterPlanetary File System (IPFS) is a giant peer-to-peer network for file storage that uses DHTs:

* Files broken into chunks and hashed
* Files addressed by a top level hash of hashes (Merkle tree)
* Hashes stored in a DHT
* Finding a file means fetching a list of hashes for the file and the locations of those hashes

This can store large amounts of data and large numbers of files/directories.
Similar to BitTorrent as a file system, since many nodes may have duplicate copies of part of a file.
No node needs more than one copy of a block.
Git works similarly;
each block is only downloaded once even if it exists across many commits.

IPFS could replace or augment HTTP with its file transfer capabilities.
It can be thought of similarly to a CDN, except that the granularity means data gets even closer to you.


## Asynchronous code

Helps respond to fast requests quickly while doing computation for longer requests on the side

Options for dealing with requests:

* New processes and threads - expensive for the computer and sometimes difficult to program
* I/O multiplexing in one concurrent thread

Concurrency is dealing with one problem at a time where possible, while parallelism is working on many problems at the same time


## asyncio

An event loop runs in a thread and executes all callbacks and tasks in that thread.
Tasks get suspended whe a task calls an `await` expression.
_Coroutines_ are components that define subroutines to be run concurrently.
Generators are the precursor to how `asyncio` works.

The `async` keyword defines a function as a coroutine.
`async` functions can call other `async` functions via `await`.

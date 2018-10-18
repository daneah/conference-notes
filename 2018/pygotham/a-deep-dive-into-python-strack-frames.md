# "A deep dive into Python stack frames" by Nikhil Marathe

## Use case

Crashpad is an out-of-process crash analyzer.
It was made for Chrome, which is written in C++.
It doesn't know Python, but can be taught to understand CPython.


## Analyzing memory

Looking into the memory for the frames doesn't produce obvious stack traces.
Iterating through the frames and getting the relevant file and line of code is what you need for debugging.
Python represents the frames in a stack that acts much like a linked list.
The head of the list is always pointed to by the current interpreter state, and each frame points to the frame above it.

# "Seventeen Million Lines of Python Later: Launching a Startup in an Investment Bank" by Garrett Walker

Bank of America built a platform that allowed developers to run tasks in parallel on a grid
without worrying about what infrastructure was providing the grid.

Collapse of the financial industry wasn't due to one cause;
as many as 25 major factors were involved.
The problem between banks also can't be modeled as a two-way trading system;
it's a large complicated network of interrelated trading.

_Quartz_ was built to abstract the multi-feed streams of risk, finance, and capital into simpler interfaces.
It includes web services, a Python object database, job scheduling, etc.
It consists of 82M lines of code, 350K compute cores, and 8.2 PB of data.


## Toolset

* Built a way to parse code into a DAG and memoize for speed
* Built a simple way to write objects to a data store and rehydrate them later

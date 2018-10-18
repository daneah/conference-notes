# I didn't know querysets could do that!
## Charlie Guo

### Ideas

* Use `.only()/.defer()` to specify the specific fields you want to select
* Use `in_bulk()` for getting specific entries by id
* Use Q() and F() for constraints and implicit references, avoiding item references, lookups, and race conditions
* F() is more specific case of general Query Expression paradigm

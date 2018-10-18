# Django for the Internet of Things
## Anna Schneider, @windupana, @wattTime

### Ideas

* Similar to the books/authors model, but with devices/observations
* IoT is mainly about timeseries data
* Librato

### Tasks

* Replace views since they aren't geared toward humans
* Puts responsibility of pushing/pulling info outside the user request/response cycle
* Two classes: monitor and control
* Best to return PKs for devices rather than an object for better asynchronous programming

### Django apps

* Devices
    * Add/remove devices
* Observations
    * analytics
* Interactions
    * logging, interface
* Vendor

### Two ways to run tasks

#### Hackathon way

* Management commands + scheduler

#### Production way

* task functions + celery
    * Distributed message queueing system for async work

##### Architecture

* Things that put messages on a message broker queue (redis or rabbitmq)
    * Web Servers
    * Scheduler
* Worker servers
* Result store (redis)

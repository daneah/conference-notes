# "From Monolithic to Serverless" by [Scott Triglia](https://www.twitter.com/scott_triglia), Yelp


## Use case
Subscription billing at Yelp
* Monthly invoicing for advertising accounts
* Business critical activity with over 100K accounts


## Subscription billing workflow
Bill all accounts -> Create invoices -> Collect all accounts


## Challenges in migration
* No good APIs in existing business processes
* Existing code far from being lambda-compatible
* Code not factored into manageable chunks to be migrated to another system


## Process for migration
Outline business process to be migrated

In AWS step functions:
* Write some JSON
* Get a state machine!
* Implement functions/activities for specific steps, either as processes on instances over API or as Lambda functions


## Benefits of AWS step functions
* Easily increase/decrease parallelism as needed
* Easy timeout handling
* Enhanced observability of outcomes of steps
* Flexible execution model allows subdivision into small pieces


## Bill all accounts
* Create chunks of accounts (runner) and bill them (worker) in parallel
* Create single step called "bill account" and build activity that bills accounts by ID/date
* Refactor "bill account" step as desired until manageable

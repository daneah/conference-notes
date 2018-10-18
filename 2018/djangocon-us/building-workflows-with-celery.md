# "Building Workflows with Celery" by Josue Balandrano Coronel

## Overview

The application acts as a producer that sends tasks to workers, which complete tasks in a process pool.


## Workflow: Login from unrecognized device

Define a chain that:
1. Checks if device has been used before (task)
1. Notifies user and saves event in history (group)
1. Checks security API (task callback)
1. Processes API response (task callback)

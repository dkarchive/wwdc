# advanced nsoperations

## exploring the wwdc app

session 226, app frameworks

- philippe hausler, foundation engineer
- dave delong, frameworks evangelist

> `NSOperation` and `NSOperationQueue`

- wwdc app

# core concepts

## NSOperationQueue

- `NSOperationQueue`: high level dispatch_queue_t
- Cancellation
- `maxConcurrentOperationCount`
- serial queue: `maxConcurrentOperationCount` = 1
- concurent queues `maxConcurrentOperationCount` = Default

## NSOperation

- high level dispatch block
- long-running task
- subclassable
- life cycle (states): -> pending -> ready -> executing (from ms to minutes and longer) -> finished .. at any point except finished can go into cancelled state

### cancellation

- `isCancelled` Boolean
- subclassing has to take care of `cancelled`
- race condition (can be finished before)
- `operationA.cancel()`

### readiness

- `isReady` Boolean
- first operation ready in the queue gets executed (can be out of order)
- make dependencies: strict ordering, implemented by readiness
- not limited by queues (can be in different queues)

``` swift
let operationA = ...
let operationB = ...
operationB.addDependency(operationA)
```

- issue: operation deadlock (setup the wrong dependencies)

- examples: wwdc app favorites, using dependencies
  - log in
  - user info
  - cloud kit access
  - save favorite

- examples: wwdc app startup
  - settings
  - version check
  - download news, sessions, beacons
  - download feedback, favorites, videos
  - save to data store

### abstraction

- operations abstract logic
- simplifies logic changes
- grand central dispatch?

# beyond the basics

## ui operations

> not just the background

- authentication
- videos
- alerts
- modal ui

## block operations

- nsoperation to execute a block
- dependencies

## generating dependencies

- create a single operation, it generates its own dependencies

## extending readiness

- adding requirements
- "only execute if"

examples 

  - network is reachable
  - access to user location
  - user is logged in

## composing operations

import data operation

- downloading and parsing 

## mutual exclusivity

- use dependencies (only one alert at once)

# sample code

- earthquakes and operations
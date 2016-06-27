# multitasking on ipad

presidio

330pm

jun 10, 2015

# presentors

brittany, springboard engineers


optimize your pap
fix memory leaks
time profiler trace
allocation instruments
great performance involves tradeoffs
instruments

memory management: understand and manage working set

> critial objects and resources you need right now

- keep it small
- might change based on context (view controllers, foreground vs background)
- dont let it grow unbounded

cpu management: main thread's top priority is responding to user events
- dont do unecessary work
- gcd / qos
 
memory warnings

- remove anything not in the working set
- clear cached data
- release images
- release view controllers

Use `NSCache`, it is memory aware


#advanced adaptive memory

jon drummond, ios springboard engineers

- memory is the most constrained resource on ios - it does not degrade gracefully (just kill the apps, dropping to springboard)

memory classification

- dirty - memory in active use - not reclaimable
- purgeable - not in use - can be reclaimed
- clean - read only, backed by files - can be reclaimed

goals

1. minimize dirty memory
2. maximize purgeable, clean

tips

- use less of it
- classify dirty memory as purgeable 

purgeable data

`NSPurgeableData`, works with system

reconsider data characteristics: cache file on disk, which is clean memory

ideal for read-only data


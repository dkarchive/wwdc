# debugging energy issues

session 708

nob hill

jun 10, 2015 at 10am

tag: #systems frameworks

# presentors

- abhinav pathak, ios power team
- pai-han huang, ios power team

> Find energy problems and fix them.

# existing tools

- osx: activity monitor, energy monitor
- ios8: battery usage ui in settings
- ios9: shows minutes on screen, and background

> how to get down in battery list


# energy fundamentals and best practices

- energy 101: energy = power & time
- app launch, app activities, app backgrounded, app suspended
- fixed cost: can be very expensive, how can we reduce it vs dynamic cost

reducing energy use

- do it never/do it less
- do it at a better time (wait for connection to power source)
- do it efficiently


# energy debugging workflow and tools

- write code and build (xcode)
  - 
  - 
- issue found: general debugger (xcode, while running, hit energy impact gauge)
  - 
  - 
- focused debugger (instruments)
  - energy diagnostics (long experiment): settings, developer/instruments - start recording, use app then stop recording - import data into instruments: shows states for gpu, wifi etc - does not pinpoing where in code
  - new tool this year: in instruments
  
- ship it (system settings)

## energy debugging priorities on ios are cpu, location networking, background

### location

- do it never/do it less
  - continuous only if absolutely needed
  - stop when finished
- do it efficiently
  - what accuracy do you require
  - which location api to use

### networking

- do it never/do it less
  - cut down transfers: cache, compress, media quality..

- do it at a better time
  - consider tolerance
  
- do it efficiently
  - networking: buffer data before syncing (mitigate fixed cost)
  
### background  
  
- do it never/do it less
  - do no run in background  
  - call background task completion handler asap

- do it efficiently
  - call energy efficient background apis (application: fetch)
  
# demo: fixing energy issues on ios

> tools to identify and improve energy

1. new toolset
  - xcode debug navigator: energy impact
  - instant and average
  - zone gauge: green, yellow, red (significant battery drop)
  - energy impact: cpu/network/location/background, red = overheard (fixed cost), blue is the use  
  - for more details: time profile, network profile, location (down to method) 
  - instruments
    - record and stop
    - shows reasons
    - go to extended details: backtrace
2. demo app
  - energy buddy: take photo, get location and weather info
  - 
  
# final thoughts
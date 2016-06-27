# building responsive and efficient apps with gcd

- 2015
- system frameworks
- session 718

## presentors

- anthony j chivetta, darwin runtime engineer
- daniel a steffen, darwin runtime engineer

> gcd introduced with snow leopard, allow you to use multiple cores

- can help with high end
- but also other platforms

- macbook without a fan
- ios9 multitasking
- watchos

# quality of service (qos)

- handling events in main thread
- gcd queue handle events asynchornously
- competing threads.. qos
  - ios8 introduced qos: ui (user interactive), in (user initiated), ut (utility), bg (background)
  - complex system resource controls
      - ui: main thread, animations
      - in: blocking
      - utility: progress
      - bg: not user visible
  

- will be used for fanless macbook, multitasking in ios9
  
# design patterns with qos

- specific example, api
- qos can be specified on blocks/queues
- dispatch_async automatically propagates qos: inferred qos
- some priority inversions are resolved automatically
- locks
- semaphores not supported

# threads, queues and run loops
# gcd and crash reports
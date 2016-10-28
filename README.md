# distributed-tracing
This repository contains code to explore distributed tracing with zipkin and linkerd


This is the architecture we're aiming for (unless we don't want to use namerd :) )

```
Application
  |
Request
  |
  V
linkerd ----logical name-----> namerd <--> Service Discovery
        <---concrete address--        <--> Dtab Storage
  |
Request
  |
  V
Destination
```

see: https://github.com/BuoyantIO/linkerd/tree/master/namerd

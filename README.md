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

## zipkin

put this in the linkerd `config/linkerd.yaml` and restart linkerd

```
tracers:
- kind: io.l5d.zipkin
  host: localhost
  port: 9411
  sampleRate: 0.02
```

run zipkin
```
java -jar zipkin.jar
```

check `192.168.33.10:9411` for tracing

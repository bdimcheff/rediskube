Stolen from [stateful app tutorial](https://github.com/kubernetes/kubernetes.github.io/tree/master/docs/tutorials/stateful-application)

# What?

I need a cluster of (generally 3) redis instances with sentinel failover.  Masters must persist across restarts, which means that redis needs to be able to write to its config file and the config needs to remain stable.

# How?

```
kubectl apply -f redis-configmap.yaml redis-sentinel-configmap.yaml
kubectl apply -f redis-services.yaml
kubectl apply -f redis-statefulset.yaml
kubectl apply -f redis-sentinel-statefulset.yaml
```

# TODO

* document what's going on
* authentication may be desirable

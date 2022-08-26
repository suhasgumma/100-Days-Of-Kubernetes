## Day 24 -- Ingress, Metrics Server & Horizantol Pod Auto Scaling

### Ingress

Ingress Exposes multiple Services through a single cloud load-balancer.

### Ingress vs Load-balancer.png

<img src="Images For Readme/Ingress vs Load-balancer.png" height = 300 width = 500>

### Ingress Fanout

<img src="Images For Readme/Ingress Fanout.png" height = 300 width = 500>

### __________________________________________________________________________________________________________________________________________________________________________________________

### Metrics Server

#### Collects resource metrics from kubelets & exposes them in K8s API server through metrics API for use by HPA & VPA

### __________________________________________________________________________________________________________________________________________________________________________________________

### Horizontal Pod Auto Scaling

HorizantolPodAutoScaler **automatically** updates workload resources to match demand.

```
Horizantol Scaling --> Deploy more Pods.
Vertical Scaling --> Assign more resources (CPU, memory, etc) to existing pods.
```

### HPA Controller 

Adjusts the desired scale of the workloads to match observed metrics (average CPU utilization, etc)

```
desiredReplicas = ceil[currentReplicas * (currentMetricValue / desiredMetricValue)]
```
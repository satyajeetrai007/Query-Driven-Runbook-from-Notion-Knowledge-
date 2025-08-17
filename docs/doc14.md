# KB: Checking for CPU Throttling

## Content
CPU throttling occurs when a container tries to use more CPU than its defined limit.

## Method 1 (Prometheus)
The best way is to monitor the `container_cpu_cfs_throttled_seconds_total` metric. A constantly increasing value indicates throttling.

## Method 2 (cAdvisor)
The kubelet's cAdvisor endpoint also exposes throttling metrics.

## Symptom
The application will feel slow or unresponsive despite the pod's overall CPU usage appearing below the limit.
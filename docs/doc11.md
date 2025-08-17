# KB: How to Set Resource Requests and Limits

## Requests
The amount of resources (CPU/memory) that Kubernetes guarantees for a pod. This is used for scheduling. If a pod requests 1 CPU, K8s will only place it on a node with at least 1 CPU available.

## Limits
The maximum amount of resources a pod can use. If a pod exceeds its memory limit, it will be terminated (`OOMKilled`). If it exceeds its CPU limit, it will be throttled.

## Best Practice
Always set requests and limits. Set `requests` equal to `limits` for critical workloads to get a `Guaranteed` QoS class.
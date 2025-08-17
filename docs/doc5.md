# SEV-3 - Node Under Memory Pressure - 2025-08-10

## Summary
A Kubernetes node in the `us-east-1a` zone reported a `MemoryPressure` taint. Kubelet began evicting pods, causing service disruptions. A logging sidecar container with no memory limits was found to be consuming all available node memory.

## Action Item
Enforce memory limits on all containers via an admission controller policy. Owner: `@platform-team`.
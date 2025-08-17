# SEV-2 - DNS Resolution Failure in Core Namespace - 2025-08-14

## Summary
Pods in the `core` namespace were unable to resolve internal service hostnames (e.g., `redis.core.svc.cluster.local`). The CoreDNS pods were in a `CrashLoopBackOff` state due to a misconfigured upstream resolver. Reverting the CoreDNS config map restored DNS resolution.

## Action Item
Add a canary deployment strategy for CoreDNS changes. Owner: `@platform-team`.
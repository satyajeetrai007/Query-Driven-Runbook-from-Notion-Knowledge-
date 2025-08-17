# SEV-1 - Expired TLS Certificate - 2025-08-16

## Summary
At 09:00 IST, all public-facing APIs began returning `503` errors. Investigation revealed the public-facing TLS certificate for `api.example.com` had expired, causing TLS handshake failures at the load balancer. The certificate was manually renewed via cert-manager to resolve the issue.

## Action Item
Automate alerts for certificates expiring within 30 days. Owner: `@sre-team`.
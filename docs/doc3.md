# SEV-2 - Ingress Controller Misconfiguration - 2025-08-13

## Summary
A new ingress rule deployed for the `billing-service` incorrectly routed all traffic for the root path (`/`) to itself, effectively hijacking traffic from all other services. Deleting the faulty ingress rule immediately resolved the issue.

## Action Item
Implement static analysis/linting for ingress YAML in the CI/CD pipeline. Owner: `@devops`.
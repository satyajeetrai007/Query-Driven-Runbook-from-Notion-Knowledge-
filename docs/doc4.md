# SEV-1 - Database Connection Pool Exhaustion - 2025-08-11

## Summary
The `user-service` began timing out on all database requests. Monitoring showed the PostgreSQL database had hit its `max_connections` limit. A downstream service was leaking connections and not closing them properly. Restarting the downstream service pods provided immediate relief.

## Action Item
Implement connection timeout settings in the `user-service` database client. Owner: `@backend-devs`.
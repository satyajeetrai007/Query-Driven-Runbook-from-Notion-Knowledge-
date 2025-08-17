# ARCH: Proposal to Switch to gRPC

## Problem
Our internal microservices communicate via REST over HTTP/1.1. This causes high latency and significant overhead due to text-based serialization (JSON) and repeated TCP handshakes.

## Proposed Solution
1. Migrate inter-service communication to use gRPC with Protocol Buffers.
2. Benefits: Binary serialization is faster, HTTP/2 allows for multiplexing requests over a single connection, and auto-generated client stubs reduce boilerplate code.
3. **Rollout Plan:** Start with the two highest-traffic services (`user-service` and `product-service`) as a pilot.
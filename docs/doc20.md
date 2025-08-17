# ARCH: Design for a New Centralized Logging Pipeline

## Problem
Developers currently have to `kubectl logs` into individual pods, which is inefficient. Logs are lost when pods are terminated.

## Proposed Solution
1. Deploy **Fluentd** as a `DaemonSet` on every Kubernetes node to collect logs.
2. Fluentd will forward all logs to a central **OpenSearch** (or Elasticsearch) cluster for storage and indexing.
3. **Kibana** will be used as the visualization and search UI for developers.
4. **Benefits:** Centralized log searching, longer retention, and the ability to create dashboards and alerts based on log content.
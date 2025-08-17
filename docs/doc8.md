# DEBUG: Slow Disk I/O on Prometheus Pod - 2025-08-07

## Notes
- Prometheus is slow and alerts are delayed. Grafana dashboards are not loading.
- `kubectl exec` into the pod and ran `iostat`. Seeing very high `%iowait`.
- The pod uses a Persistent Volume Claim (PVC) on our cloud provider.
- Checked the volume type. It's a standard HDD (`standard`) instead of an SSD (`gp3`). The IOPS are too low for the write-heavy workload.
- **Action:** Planned maintenance to migrate the Prometheus data to a new `gp3` SSD volume.
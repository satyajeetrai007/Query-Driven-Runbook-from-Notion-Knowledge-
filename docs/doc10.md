# DEBUG: HPA Not Scaling Deployment - 2025-08-04

## Notes
- The `api-gateway` deployment is under heavy load (90% CPU), but the Horizontal Pod Autoscaler (HPA) is not adding new pods.
- `kubectl describe hpa api-gateway` shows `unable to read metric for pod ... no metrics known for pod`.
- The Kubernetes metrics-server is not running correctly in the cluster.
- `kubectl get pods -n kube-system` showed the `metrics-server` pod was failing. Logs indicated a problem with its certificate.
- **Action:** Re-installed the metrics-server. HPA started fetching metrics and scaled the deployment correctly.
# DEBUG: Liveness probe failed for cart-service - 2025-08-09

## Notes
- Symptom: `cart-service` pods are restarting every 5 minutes.
- `kubectl describe pod cart-service-xyz` shows multiple events for `Liveness probe failed: Get "http://:8080/health": context deadline exceeded`.
- The `/health` endpoint is slow to respond because it makes a downstream call to a slow DB. The liveness probe timeout is only 1 second.
- **Conclusion:** The probe is too aggressive. The app isn't dead, just slow.
- **Action:** Increased liveness probe `timeoutSeconds` to 5s and `periodSeconds` to 10s.
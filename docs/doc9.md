# DEBUG: Service Mesh (Istio) Routing Issue - 2025-08-05

## Notes
- `service-a` is getting 503 errors when calling `service-b`, but `service-b` pods are healthy.
- Both services are in the Istio service mesh.
- Used `istioctl proxy-config routes ...` to inspect the Envoy config. The route for `service-b` was not present in `service-a`'s proxy.
- Found an Istio `VirtualService` that was configured with a specific `hosts` entry that didn't match the internal service name.
- **Action:** Corrected the `hosts` field in the `VirtualService` YAML and reapplied it. Traffic started flowing.
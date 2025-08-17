# KB: Understanding Kubernetes Network Policies

## Content
Network Policies act as a firewall for pods. By default, all pods in a cluster can talk to each other.
To control traffic, you apply `NetworkPolicy` objects that specify ingress (incoming) and egress (outgoing) rules.
A common strategy is to apply a "deny-all" default policy to a namespace and then explicitly allow required traffic between services.

## Example
To allow traffic from the `api` pods to the `user-service` pods on port 80, you would create a policy with an ingress rule targeting the `user-service` pod labels.
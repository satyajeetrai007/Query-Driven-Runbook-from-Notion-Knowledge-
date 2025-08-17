# KB: How to Force a Rolling Restart of a Deployment

## Content
If you need to restart all pods in a deployment (e.g., to pick up a new ConfigMap), you can trigger a rolling update without changing the image.

## Command
`kubectl rollout restart deployment/<deployment-name>`
This command will gracefully terminate old pods and create new ones, respecting your deployment strategy (e.g., `maxUnavailable`).
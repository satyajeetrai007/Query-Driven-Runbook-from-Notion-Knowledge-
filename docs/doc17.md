# Slack: #dev - 2025-08-12 - Need to increase resources for checkout-service

## Content
- **User E:** "@sre-team Can we please bump the memory requests for the `checkout-service` from 256Mi to 512Mi? We're seeing some OOMKills during peak traffic."
- **User F:** "Sure. Have you done any profiling to see where the memory is going?"
- **User E:** "Yes, it's an in-memory cache we added. 512Mi should be the new baseline."
- **User F:** "Okay, PR is up. Approving and deploying."
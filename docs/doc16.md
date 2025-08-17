# Slack: #cloud-costs - 2025-08-15 - S3 Bill Spiked

## Content
- **User C:** "Team, our S3 bill for last month is 50% higher than usual. The main cost is data transfer."
- **User D:** "I'll check. It looks like the `log-archive` job is transferring logs between two S3 buckets that are in different regions. That's expensive."
- **User C:** "Why would it do that?"
- **User D:** "The job is running on a pod in `us-east-1` but the destination bucket is in `eu-west-1`. We should deploy the job to a cluster in the same region as the bucket."
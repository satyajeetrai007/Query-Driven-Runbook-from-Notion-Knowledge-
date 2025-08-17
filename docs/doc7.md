# DEBUG: IAM Role Permission Denied for S3 Access - 2025-08-08

## Notes
- The `image-processor` pod is failing to read from an S3 bucket.
- Pod logs show `botocore.exceptions.ClientError: An error occurred (AccessDenied) when calling the GetObject operation`.
- Verified the pod is using the correct service account, which is annotated for an IAM role.
- Checked the IAM role in AWS. The policy was missing the `s3:GetObject` permission.
- **Action:** Added the required permission to the IAM policy. Pods started processing images correctly after a restart.
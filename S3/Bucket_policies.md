# Definition:
Bucket policies are JSON-based access control policies attached directly to S3 buckets.

Use Case
- Deny or allow access to specific users or IP ranges
- Enforce HTTPS-only requests

Example: Deny HTTP (allow HTTPS only)
```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "DenyInsecureTransport",
      "Effect": "Deny",
      "Principal": "*",
      "Action": "s3:GetObject",
      "Resource": "arn:aws:s3:::my-bucket-name/*",
      "Condition": {
        "Bool": {
          "aws:SecureTransport": "false"
        }
      }
    }
  ]
}

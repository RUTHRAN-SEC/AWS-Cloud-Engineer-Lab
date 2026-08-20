# Day 3 Troubleshooting Report

## Support Ticket

> "I can upload files but cannot delete them. Is the S3 bucket broken?"

## Investigation

```text
Investigation
     ↓
Check IAM identity
     ↓
Check attached policies
     ↓
Check requested action
     ↓
Check resource
     ↓
Determine authorization result
     ↓
Explain expected behavior
```

- [ ] Confirmed the IAM identity making the request (`developer-day02`)
- [ ] Reviewed attached policies (`Day03-Developer-S3-LeastPrivilege`)
- [ ] Confirmed the requested action (`s3:DeleteObject`)
- [ ] Confirmed the target resource (bucket/object ARN)
- [ ] Confirmed the policy does not grant `s3:DeleteObject`

### Root Cause
The bucket itself is fine. The developer IAM policy was intentionally written without s3:DeleteObject. That action was never part of the approved permissions, so deletion attempts are denied by design. This is not a bug or misconfiguration — it’s the expected outcome under least privilege.

### Resolution
No changes are required. The denial is correct behavior. The hardened policy (Day03-Developer-S3-LeastPrivilege) is working exactly as intended.

## Security Validation

Confirms the hardened policy is working as intended: allowed actions (list/upload/download) succeed, and everything outside the approved scope (delete, bucket policy changes, other buckets) is denied.

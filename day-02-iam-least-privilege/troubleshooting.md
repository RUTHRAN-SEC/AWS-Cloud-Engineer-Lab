# Day 2 Troubleshooting Report

## Problem

Developer initially cannot access S3.

## Investigation

What was checked, in order:

- IAM user (`developer-day02`) exists and is enabled
- IAM permissions attached to the user (initially: none)
- Policy existence and content
- S3 bucket name and region
- Resource ARN format (bucket-level vs object-level)
- Specific S3 actions granted

### Root Cause
The developer initially could not access the S3 bucket because no IAM policy was attached. By default, IAM users have no permissions, so all S3 actions (ListBucket, GetObject, PutObject) were implicitly denied.

### Resolution
You created and attached the DeveloperDay02S3Access policy.
This policy explicitly granted:

- s3:ListBucket → to list objects inside the bucket.
- s3:GetObject → to download objects.
- s3:PutObject → to upload objects.

The policy was scoped to the single bucket cloud-engineer-lab-day02-123321.

### Validation
After attaching the policy:

- List bucket → PASS (developer could see objects).
- Upload object → PASS (developer uploaded developer-test.txt).
- Download object → PASS (developer downloaded successfully).

### Security Validation
The developer was intentionally denied:

- s3:DeleteObject → cannot delete objects.
- Access to other buckets → not granted.
- Bucket configuration changes (e.g., PutBucketPolicy, PutBucketPublicAccessBlock).
- IAM permissions → not granted.

This enforces the principle of least privilege.

### Secondary Exercise — Missing 
**s3:ListBucket**
When s3:ListBucket was temporarily removed:

- Upload directly to a known object key → still worked (developer could upload if they knew the exact path).
- List bucket contents → failed (developer could not see objects in the bucket).
- Error observed → “Access Denied” when trying to list objects.

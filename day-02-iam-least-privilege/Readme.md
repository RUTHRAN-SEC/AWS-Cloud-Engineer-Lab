# Day 2  IAM Least Privilege

## Ticket

**AWS-002 — Developer S3 Access**

> A developer needs to upload and download objects from one application S3 bucket, but must not be able to delete objects or access other buckets.

## Objective

Create a least-privilege IAM policy that allows a developer to work with one S3 bucket without granting unnecessary permissions.

## Business Requirement

The developer needs to:

- List the application bucket
- Upload objects
- Download objects

The developer must not:

- Delete objects
- Access other buckets
- Modify bucket configuration
- Modify IAM permissions

## Implementation

```text
IAM User:
developer-day02

IAM Policy:
DeveloperDay02S3Access

S3 Bucket:
<your bucket name>
```

Policy JSON: [`policy/developer-s3-access.json`](./policy/developer-s3-access.json)

## Allowed Actions

- `s3:ListBucket`
- `s3:GetObject`
- `s3:PutObject`

## Not Granted

- `s3:DeleteObject`
- `s3:DeleteBucket`
- `s3:PutBucketPolicy`
- `s3:PutBucketPublicAccessBlock`
- IAM permissions

## Validation

| Action | Result |
|---|---|
| List bucket | PASS |
| Upload | PASS |
| Download | PASS |
| Delete | DENIED |
| Access to another bucket | DENIED / NOT GRANTED |

## Security Principle

Least privilege was applied by granting only the permissions required for the developer's task. No explicit `Deny` was needed for delete — the absence of `s3:DeleteObject` in the policy results in an implicit deny.

## Evidence

Screenshots are stored in [`/screenshots`](./screenshots), with all sensitive details redacted.

| # | File | Shows |
|---|------|-------|
| 1 | `01-s3-bucket.png` | S3 bucket created with block public access + versioning |
| 2 | `02-developer-permissions.png` | Least-privilege policy attached to `developer-day02` |
| 3 | `03-upload-success.png` | Developer successfully uploads an object |
| 4 | `04-download-success.png` | Developer successfully downloads an object |
| 5 | `05-delete-denied.png` | Developer denied on delete attempt |

## Troubleshooting

See [`troubleshooting.md`](./troubleshooting.md) for the initial "developer cannot access S3" investigation.


## Lessons Learned

- Bucket vs Object ARNs  
You must use the bucket ARN (arn:aws:s3:::bucket-name) for bucket‑level actions like s3:ListBucket, and the object ARN (arn:aws:s3:::bucket-name/*) for object‑level actions like s3:GetObject and s3:PutObject. Mixing them up is a common cause of AccessDenied.

- Implicit deny principle  
If you don’t explicitly grant a permission, it is denied by default. You don’t need to write explicit Deny statements for every action you don’t want — simply omit them.

- Least privilege design  
The developer was given only the actions required (ListBucket, GetObject, PutObject) for one bucket. They cannot delete objects or touch other buckets, which enforces the security principle of least privilege.

- Policy troubleshooting  
Removing s3:ListBucket showed that the developer could still upload/download if they knew the object path, but couldn’t list contents. This highlights how different actions map to different resources and why troubleshooting requires checking both.

- Console usability vs security  
Adding s3:ListAllMyBuckets improves console usability (developer can see the bucket list), but it’s not strictly required for least privilege. This teaches the trade‑off between user experience and tight security controls.

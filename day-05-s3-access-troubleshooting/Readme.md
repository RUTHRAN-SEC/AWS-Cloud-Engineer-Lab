# Day 5 S3 Access Troubleshooting & Root Cause Analysis

## Ticket

**AWS-005: Developer Cannot Upload to S3**

> "I can see the application S3 bucket, but my application cannot upload files anymore. It worked previously."

## Objective

Investigate a reported upload failure without simply granting more permissions find the smallest change that fixes the problem, then prove it with tests.

## Rules Followed

- No `AdministratorAccess`
- No `AmazonS3FullAccess`
- No `s3:*`
- Bucket not made public
- Block Public Access left enabled
- Existing security controls left intact

## Baseline (before the incident)

| Action | Result |
|---|---|
| List bucket | PASS |
| Upload | PASS |
| Download | PASS |
| Delete | DENIED |

## Incident

`s3:PutObject` was intentionally removed from `Day03-Developer-S3-LeastPrivilege` to reproduce a realistic access failure. Full details in [`incident-report.md`](./incident-report.md).

## Investigation

Step by  step evidence gathering (IAM policy, resource ARN, bucket policy, encryption) in [`investigation.md`](./investigation.md).

## Root Cause

`s3:PutObject` had been removed from the developer's least-privilege IAM policy. Full analysis in [`root-cause.md`](./root-cause.md).

## Remediation

`s3:PutObject` restored, scoped to the object resource ARN only no broader permissions granted. Full change record in [`remediation.md`](./remediation.md).

## Post-fix Validation

| Action | Result |
|---|---|
| List bucket | PASS |
| Upload | PASS |
| Download | PASS |
| Delete | DENIED |

## Troubleshooting Flow Practiced

```text
Reproduce → Identify action → Check IAM → Check resource ARN
   → Check bucket policy → Check encryption → Find root cause
   → Minimal remediation → Retest → Document
```

## Evidence

Screenshots are stored in [`/screenshots`](./screenshots), with all sensitive details redacted.

| # | File | Shows |
|---|------|-------|
| 1 | `01-access-denied.png` | Reproduced `AccessDenied` on upload |

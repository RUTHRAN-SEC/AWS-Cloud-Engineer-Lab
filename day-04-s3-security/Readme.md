# Day 4 S3 Operations & Security

## Ticket

**AWS-004: Secure an Application S3 Bucket**

> Review the bucket configuration, ensure objects are protected from accidental deletion, verify encryption and public-access controls, and implement an appropriate lifecycle policy.

## Objective

Inspect the Day 2 application bucket, identify gaps, harden its configuration, test recovery behavior, and document everything.

## Scope

- Bucket: `cloud-engineer-lab-day02-123321`
- No new paid infrastructure created
- Existing bucket reused across labs going forward

## Tasks Completed

- [x] Reviewed S3 bucket security posture
- [x] Verified Block Public Access
- [x] Verified Object Ownership (bucket owner enforced)
- [x] Verified default encryption
- [x] Verified versioning
- [x] Tested object version recovery
- [x] Reviewed/configured a lifecycle rule for noncurrent versions
- [x] Documented findings

## Summary of Findings

See [`security-review.md`](./security-review.md) for the full per-control review (public access, object ownership, encryption, versioning, bucket policy, lifecycle).

## Version Recovery Test

See [`recovery-test.md`](./recovery-test.md) for the accidental-overwrite simulation and recovery procedure.

## Evidence

Screenshots are stored in [`/screenshots`](./screenshots), with all sensitive details redacted.

| # | File | Shows |
|---|------|-------|
| 1 | `01-block-public-access.png` | Block Public Access fully enabled |
| 2 | `02-object-ownership.png` | Object Ownership set to "Bucket owner enforced" |
| 3 | `03-default-encryption.png` | Default server-side encryption enabled |
| 4 | `04-object-versions.png` | Multiple object versions visible for `version-test.txt` |



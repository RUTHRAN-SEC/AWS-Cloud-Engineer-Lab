# Day 3 IAM Policy Hardening

## Ticket

**AWS-003: Excessive Developer Permissions**

> A security review found a developer with an `s3:*` / `Resource: *` policy. The developer only needs to work with one S3 bucket. Investigate, identify the risks, replace with least-privilege permissions, and prove the developer can still do their job.

## Objective

Identify and remediate excessive S3 permissions assigned to a developer.

## Initial Security Finding

The developer was assigned:

```text
Action:
s3:*

Resource:
*
```

This violated the principle of least privilege.

See [`policies/insecure-policy.json`](./policies/insecure-policy.json) — kept in the repo as a labeled, intentionally insecure example, never used in production.

## Business Requirement

The developer only requires:

- List application bucket
- Upload objects
- Download objects

The developer does not require:

- Delete objects
- Delete bucket
- Modify bucket policies
- Modify public access settings
- Access unrelated buckets

## Security Risks

Full detail in [`risk-analysis.md`](./risk-analysis.md).

- **Excessive actions** — `s3:*` grants unnecessary permissions
- **Excessive resource scope** — `Resource: "*"` creates an unnecessarily broad permission scope
- **Destructive operations** — potential to delete objects/buckets
- **Configuration modification** — potential to change bucket-level security settings
- **Blast radius** — compromised developer credentials could provide excessive access to S3 resources

## Remediation

Replaced the broad policy with a resource-scoped policy containing only:

- `s3:ListBucket`
- `s3:GetObject`
- `s3:PutObject`

See [`policies/hardened-policy.json`](./policies/hardened-policy.json).

## Validation

| Test | Expected | Result |
|---|---|---|
| List bucket | Allow | PASS |
| Upload object | Allow | PASS |
| Download object | Allow | PASS |
| Delete object | Deny | PASS |
| Modify bucket policy | Deny | PASS |
| Delete bucket | Deny | PASS |

Also validated with the IAM Policy Simulator directly against the hardened policy (see screenshot 06).

## Security Outcome

The developer's permissions were reduced from broad S3 access (`s3:*` on `Resource: *`) to only the three actions required for the approved workflow, scoped to the specific bucket and its objects.

## Key Lesson

Least privilege reduces the blast radius of compromised credentials and prevents unnecessary administrative actions.

## Evidence

Screenshots are stored in [`/screenshots`](./screenshots), with all sensitive details redacted.

| # | File | Shows |
|---|------|-------|
| 1 | `01-insecure-policy.png` | The intentionally broad `s3:*` policy |
| 2 | `02-policy-review.png` | Permission review of the developer's attached policy |
| 3 | `03-hardened-policy.png` | The scoped least-privilege policy |
| 4 | `04-allowed-test.png` | Allowed actions passing (list/upload/download) |
| 5 | `05-denied-test.png` | Denied action (delete) |
| 6 | `06-policy-simulator.png` | IAM Policy Simulator results against the hardened policy |

## Troubleshooting

See [`troubleshooting.md`](./troubleshooting.md) for the "developer can upload but not delete" support ticket investigation.

##  Things to Do 

- [ ] Insecure policy detached from `developer-day02`
- [ ] Hardened policy attached
- [ ] No credentials committed to GitHub


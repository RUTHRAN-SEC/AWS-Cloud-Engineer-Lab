# Day 1 AWS Account Security & Cost Guardrails

## Ticket

**AWS-001: Secure a New AWS Environment**

> Joined a company as a junior Cloud Engineer and was given an AWS account. Before deploying any infrastructure, the account must be secured, safe access established, and cost protection configured.

## Objective

Secure a new AWS environment before deploying any infrastructure.

## Tasks Completed

- [x] Enabled root account MFA
- [x] Confirmed no root access keys exist / were created
- [x] Created a dedicated IAM administrative identity (`cloud-engineer-admin`)
- [x] Tested sign-in and console access with the IAM identity
- [x] Configured a zero-spend AWS Budget
- [x] Configured a secondary cost-warning budget
- [x] Reviewed AWS Free Tier usage
- [x] Identified and recorded the active AWS region

## Security Controls

### Root Account
- MFA enabled via authenticator app
- Not used for normal daily operations going forward
- No root access keys created

### IAM
- Dedicated daily administrative identity created: `cloud-engineer-admin`
- `AdministratorAccess` attached only because this is an isolated personal learning account
- This is a temporary model least-privilege roles (Cloud Engineer → ReadOnly → service-specific) will replace it in a later lab

### Cost Protection
- Zero spend budget configured to catch any unexpected charge
- Secondary warning budget small dollar threshold configured as a second layer of detection
- Free Tier usage dashboard reviewed

### Region
- Active AWS region: `(Mumbai) — ap-south-1`

## Evidence

Screenshots are stored in [`/screenshots`](./screenshots), with all sensitive details (account ID, ARNs, emails) redacted.

| # | File | Shows |
|---|------|-------|
| 1 | `01-root-mfa-enabled.png` | Root account MFA enabled |
| 2 | `02-iam-admin-login.png` | Signed in as IAM identity, not root |
| 3 | `03-free-tier-usage.png` | Free Tier usage dashboard |

## Lessons Learned

See [`lessons-learned.md`](./lessons-learned.md).

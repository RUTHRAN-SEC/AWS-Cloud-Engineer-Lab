# AWS Cloud Engineer Daily Lab

This repository is a running portfolio of hands on AWS Cloud Engineering labs, documented day by day.

Each day represents a real world ticket scenario: securing an account, configuring access control, deploying infrastructure, troubleshooting, and applying cloud security best practices the kind of work a junior Cloud Engineer would actually be assigned.

## Structure

```text
AWS-Cloud-Engineer-Lab/
│
├── README.md                      
│
├── day-01-account-security/
│   ├── README.md                   ← ticket summary + tasks completed
│   ├── screenshots/                ← evidence of the work done (no secrets)
|   |   ├── 01-root-mfa-enabled.png
│   │   ├── 02-iam-admin-login.png
│   │   └── 03-free-tier-usage.png
│   └── lessons-learned.md          ← reflection of what learned thought out the processes 
│
├── day-02-iam-least-privilege/
├── README.md
├── policy/
│   └── developer-s3-access.json
├── screenshots/
│   ├── 01-s3-bucket.png
│   ├── 02-developer-permissions.png
│   ├── 03-upload-success.png
│   ├── 04-download-success.png
│   └── 05-delete-denied.png
└── troubleshooting.md
│
├── day-03-iam-policy-hardening/
├── README.md
├── policies/
│   ├── insecure-policy.json
│   └── hardened-policy.json
├── risk-analysis.md
├── troubleshooting.md
└── screenshots/
       ├── 01-insecure-policy.png
       ├── 02-policy-review.png
       ├── 03-hardened-policy.png
       ├── 04-allowed-test.png
       └── 05-denied-test.png
```

## Ground rules followed across all days

- No secrets, passwords, access keys, or account IDs are ever committed.
- No paid infrastructure is deployed without explicit intent — Free Tier / cost guardrails first.
- Root credentials are for emergency/account-management use only; daily work uses IAM identities.
- Every lab is documented with screenshots (redacted where necessary) and a written lessons-learned reflection.

## Progress Log

| Day | Topic | Status |
|-----|-------|--------|
| 01 | AWS Account Security & Cost Guardrails | Completed |
| 02 | IAM Access Control & Least Privilege | Completed |
| 03 | IAM Least Privilege Policy Hardening | Completed |
| 04 | S3 Operations & Security | Upcoming |
| 05 | S3 Access Troubleshooting | Upcoming |
| 06 | CloudWatch Monitoring & Dashboards | Upcoming |
| 07 | Incident #001 — S3 Object Access Failure | Upcoming |
| 08 | AWS Lambda Fundamentals | Upcoming |
| 09 | S3 + Lambda Event-Driven Architecture | Upcoming |
| 10 | Lambda Troubleshooting & Root Cause Analysis | Upcoming |
| 11 | EventBridge Event-Driven Automation | Upcoming |
| 12 | SNS Operational Alerts | Upcoming |
| 13 | EventBridge + Lambda + SNS Automation | Upcoming |
| 14 | Incident — Lambda Configuration Failure | Upcoming |
| 15 | CloudFormation Infrastructure as Code | Upcoming |
| 16 | CloudFormation Parameters & Reusable Templates | Upcoming |
| 17 | Secure Infrastructure as Code | Upcoming |
| 18 | CloudFormation Deployment Troubleshooting | Upcoming |
| 19 | Infrastructure Change Management | Upcoming |
| 20 | GitHub Actions + CloudFormation Validation | Upcoming |
| 21 | Secure Serverless Infrastructure Project | Upcoming |
| 22 | CloudTrail & AWS API Activity Investigation | Upcoming |
| 23 | CloudTrail S3 Configuration Investigation | Upcoming |
| 24 | AWS Config & Configuration Compliance | Upcoming |
| 25 | Cloud Security Review & Hardening | Upcoming |
| 26 | AWS Cost Investigation & Optimization | Upcoming |
| 27 | Disaster Recovery & S3 Version Recovery | Upcoming |
| 28 | Incident #003 — Serverless Notification Failure | Upcoming |
| 29 | Final AWS Cloud Engineer Architecture | Upcoming |
| 30 | Cloud Engineer Portfolio Project | Upcoming |

## About

This log is built as a public portfolio to demonstrate practical, ticket-driven AWS engineering skills — not just certifications.


### AUTHOR
#### RUTHRAN-SEC (**AWS Certified Cloud Practitioner**)

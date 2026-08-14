# AWS Cloud Engineer — Daily Lab

This repository is a running portfolio of hands on AWS Cloud Engineering labs, documented day by day.

Each day represents a real world ticket scenario: securing an account, configuring access control, deploying infrastructure, troubleshooting, and applying cloud security best practices the kind of work a junior Cloud Engineer would actually be assigned.

## Structure

```text
aws-cloud-engineer-daily-lab/
│
├── README.md
│
├── Day 01 Account Security/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-02-iam-access-control/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-03-iam-least-privilege/
│   ├── README.md
│   ├── policies/
│   │   ├── before-policy.json
│   │   └── after-policy.json
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-04-s3-operations/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-05-s3-troubleshooting/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-06-cloudwatch-monitoring/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-07-incident-001-s3-access/
│   ├── README.md
│   ├── incident-report.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-08-lambda/
│   ├── README.md
│   ├── src/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-09-s3-lambda/
│   ├── README.md
│   ├── src/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-10-lambda-troubleshooting/
│   ├── README.md
│   ├── incident-report.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-11-eventbridge/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-12-sns-alerting/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-13-automation/
│   ├── README.md
│   ├── src/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-14-incident-002-lambda/
│   ├── README.md
│   ├── incident-report.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-15-cloudformation/
│   ├── README.md
│   ├── templates/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-16-cloudformation-parameters/
│   ├── README.md
│   ├── templates/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-17-secure-iac/
│   ├── README.md
│   ├── templates/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-18-cloudformation-troubleshooting/
│   ├── README.md
│   ├── templates/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-19-infrastructure-change/
│   ├── README.md
│   ├── templates/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-20-github-actions/
│   ├── README.md
│   ├── .github/
│   │   └── workflows/
│   ├── templates/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-21-secure-serverless-infrastructure/
│   ├── README.md
│   ├── templates/
│   ├── src/
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-22-cloudtrail/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-23-cloudtrail-investigation/
│   ├── README.md
│   ├── investigation-report.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-24-aws-config/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-25-security-hardening/
│   ├── README.md
│   ├── security-review.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-26-cost-investigation/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-27-disaster-recovery/
│   ├── README.md
│   ├── recovery-procedure.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-28-incident-003-serverless/
│   ├── README.md
│   ├── incident-report.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-29-final-architecture/
│   ├── README.md
│   ├── architecture.md
│   ├── architecture.png
│   ├── screenshots/
│   └── lessons-learned.md
│
├── day-30-portfolio-project/
│   ├── README.md
│   ├── screenshots/
│   └── lessons-learned.md
│
├── incidents/
│   ├── incident-001-s3-access.md
│   ├── incident-002-lambda-failure.md
│   └── incident-003-serverless-notification.md
│
├── security/
│   ├── security-review.md
│   └── hardening-checklist.md
│
├── cost-management/
│   ├── cost-controls.md
│   └── free-tier-monitoring.md
│
└── cloudformation/
    ├── templates/
    └── README.md                    
```

## Ground rules followed across all days

- No secrets, passwords, access keys, or account IDs are ever committed.
- No paid infrastructure is deployed without explicit intent — Free Tier / cost guardrails first.
- Root credentials are for emergency/account-management use only; daily work uses IAM identities.
- Every lab is documented with screenshots (redacted where necessary) and a written lessons-learned reflection.


## Progress log

| Day | Topic | Status |
|-----|-------|--------|
| 01 | AWS Account Security & Cost Guardrails | Complete |
| 02 | IAM Access Control & Least Privilege | Upcoming |
| 03 | IAM Least Privilege Policy Hardening | Upcoming |
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
| 14 | Incident #002 — Lambda Configuration Failure | Upcoming |
| 15 | CloudFormation Infrastructure as Code |  Upcoming |
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

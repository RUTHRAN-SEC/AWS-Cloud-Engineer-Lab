# Day 3 Risk Analysis

[`policies/insecure-policy.json`](./policies/insecure-policy.json)

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "TemporaryDeveloperAccess",
      "Effect": "Allow",
      "Action": "s3:*",
      "Resource": "*"
    }
  ]
}
```

## Risk 1: Excessive actions

`s3:*` grants far more permissions than the developer needs — every S3 action the service authorization model covers, not just list/upload/download.

## Risk 2: Excessive resources

`"Resource": "*"` doesn't restrict access to the application bucket. The permissions apply across all S3 resources the identity can reach, not just the one bucket required for the job.

## Risk 3: Destructive operations

The policy can potentially allow actions such as object deletion and other bucket-level operations that were never part of the approved business requirement.

## Risk 4: Configuration modification

Depending on the specific action/resource authorization, the developer could potentially modify bucket-level configuration (e.g. bucket policy, public access settings).

## Risk 5: Blast radius

If the developer's credentials are compromised, an attacker inherits far more S3 access than the job actually requires.

> **Least privilege reduces blast radius.**


The policy fails least privilege on both dimensions that matter **actions** and **resources** and should be replaced with a scoped policy limited to the three actions and the one bucket the developer actually needs. [`policies/hardened-policy.json`](./policies/hardened-policy.json).

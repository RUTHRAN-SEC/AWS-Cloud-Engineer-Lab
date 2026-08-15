# Day 1 — Lessons Learned

Reflection questions from ticket AWS-001. 

### 1. Why shouldn't the AWS root account be used for everyday administration?
The AWS root account should never be used for everyday administration because it has unrestricted, unlimited access to all resources. If compromised or misused, attackers gain complete control of your environment, making it a high risk security practice. Instead, daily work should be done with IAM users or roles that follow least privilege principles. 

### 2. Why is MFA important for a privileged AWS identity?
Multi Factor Authentication is critical for any privileged AWS identity like the root account or IAM administrators, Because it adds a second layer of defense beyond just a password.

### 3. Why should cost monitoring be configured before building infrastructure?
Because AWS costs can grow quickly and unexpectedly, its important to set up cost monitoring before building infrastructure.

### 4. What is the difference between an AWS root user and an IAM identity?
- The root user is the superuser of AWS it exists by default and has unlimited power.
- An IAM identity user, group, or role is created to perform daily tasks with controlled permissions.


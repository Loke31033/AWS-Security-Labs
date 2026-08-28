# AWS IAM Security & Least Privilege Lab

## Project Overview

This project demonstrates practical AWS Identity and Access Management (IAM) security using a controlled AWS lab environment.

The objective was to understand how IAM identities, groups, policies, MFA, least privilege, policy evaluation, and IAM Access Analyzer can be used to secure cloud environments.

The project follows a practical security workflow:

> Configure → Test → Misconfigure → Detect → Investigate → Remediate → Retest

---

## Objectives

- Understand AWS IAM fundamentals
- Create IAM users and groups
- Implement group-based access control
- Apply the principle of least privilege
- Create a customer-managed IAM policy
- Test IAM permissions using the IAM Policy Simulator
- Identify excessive permissions
- Remediate excessive IAM privileges
- Configure MFA for IAM identities
- Configure IAM Access Analyzer
- Document security findings and remediation

---

## AWS Services Used

- AWS IAM
- IAM Policy Simulator
- IAM Access Analyzer

---

## Lab Architecture

```text
                         AWS Account
                              |
                             IAM
                              |
                 +------------+------------+
                 |                         |
                 v                         v
       CloudSecurity-Analysts        IAM Access Analyzer
                 |
                 v
        cloudsec-analyst
                 |
                 v
   CloudSecurityAnalyst-ReadOnly-IAM
                 |
          +------+------+
          |             |
          v             v
      iam:Get*      iam:List*
          |             |
          +------+------+
                 |
                 v
          Read-only IAM
             access
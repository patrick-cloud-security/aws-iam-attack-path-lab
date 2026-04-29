$ AWS IAM Attack Path Lab

## Overview

This lab demonstrates real-world AWS cloud security attack paths and how to defend against them. 

## Attack Paths 

### 1. SSM Run Command (Remote Code Execution)

IAM user --> ssm:SendCommand --> EC2 executes command as root --> IMDS --> credential retrieval

###2 2. PassRole Priviege Escalation

IAM user --> iam:PassRole + ec2:RunInstances --> EC2 with admin role --> IMDS --> admin credentials 

## Key Lessons

- IAM permissions define blast radius
- ssm:SendCommand acts as remote code execution
- IMDS is a credential source
- iam:PassRole is dangerous when combined with compute
- CloudTrail logs control plane, not everything in the instance

## Defensive Controls

- Remove AdministratorAccess from users
- Use least privilege policies
- Restrict ssm:SendCommand
- Scope iam:PassRole
- Separate dev and prod accounts

## Status

Work in progress. Expanding into IAM guardrails and Terraform-based security design.

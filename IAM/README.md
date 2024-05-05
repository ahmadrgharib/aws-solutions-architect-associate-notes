# AWS Identity and Access Management (IAM) Guide

## IAM Overview

- IAM allows managing access to AWS services and resources securely.
- Users, Groups, Roles, and Policies are core IAM components.

### IAM Users

- IAM Users can belong to different groups.
- Users inherit policies from groups.
- Policies can be attached directly to users or added inline.

### IAM Password Policy

- Requires upper case characters, numbers, symbols, etc.
- Includes password expiration and minimum length.

### Multi-Factor Authentication (MFA)

- Highly recommended for added security.
- Options include Virtual MFA (Authy), Universal 2nd Factor security key (U2F like Yubikey), and hardware by Gemaldo.

### Access Keys

- Used for CLI and SDK access.
- Consist of Access Key ID and Access Key Secret.
- Created per user.

### AWS CloudShell

- Terminal alternative for issuing commands using AWS CLI in the cloud.

## IAM Roles for AWS Services

- Assign permissions to AWS Services.
- Similar to users but used by AWS Services.
- Common roles include EC2 Instance role and Lambda Function role.

## IAM Security Tools

- IAM Credential reports (Account level).
- IAM Access Advisor (User level).

## IAM Best Practices

- Avoid using the Root account.
- Create IAM users.
- Use groups to assign policies.
- Utilize User Roles for AWS Services.
- Keep Access Keys secret.

## IAM Roles vs Resource Based Policies

- When assuming a role, original permissions are relinquished.
- Resource-based policies do not require giving up permissions.
- Examples: Lambda, SNS, SQS for resource-based policies; Kinesis stream, Systems Manager Run Command for IAM roles.

## AWS Cognito

- Establish a user base for web or mobile apps.
- Enables row-level security in DynamoDB.
- Allows integration with API Gateway or Application Load Balancer.
- Features simple login, password reset, email & phone number verification, and MFA.
- Supports federated identities from Facebook, Google, SAML, etc.

## AWS IAM Identity Center

- Successor to AWS Single Sign-On.
- Provides single sign-on for:
  - AWS accounts in AWS Organizations.
  - Business cloud applications (e.g., Salesforce, Box, Microsoft 365).
  - SAML2.0-enabled applications.
  - EC2 Windows Instances.
- Supports built-in identity store and third-party providers like Active Directory, OneLogin, Okta.
- Offers fine-grained permissions, multi-account permissions, application assignments, and attribute-based access control (ABAC).

## AWS Directory Services

- AWS Managed Microsoft AD: Create and manage AD in AWS, establish trust connections with on-premises AD.
- AD Connector: Proxy to redirect to on-premises AD, supports MFA.
- Simple AD: AD-compatible managed directory on AWS, cannot be joined with on-premises AD.

## AWS Control Tower

- Simplifies setting up and governing secure and compliant multi-account AWS environments.
- Utilizes AWS Organizations to create accounts.
- Benefits include automated environment setup, ongoing policy management, policy violation detection, and compliance monitoring.
- Guardrails provide ongoing governance with preventive and detective measures.

## Reminders

- Some AWS services require IAM Roles for actions performed on your behalf.
- IAM Credentials report lists IAM Users and their credential status.
- IAM Users access AWS services using credentials.
- Use the root account sparingly; prefer IAM Users for everyday tasks.
- IAM Policy statement components: Sid, Effect, Principal, Action, Resource, and Condition. Version is part of the IAM Policy.
- Amazon Cognito facilitates federating mobile user accounts and granting IAM permissions.


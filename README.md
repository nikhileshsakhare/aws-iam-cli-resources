# AWS IAM Automation with AWS CLI

This project demonstrates how to use the AWS CLI to manage AWS Identity and Access Management (IAM) resources, including users, groups, customer-managed policies, and IAM roles for EC2.

## What this project does

- Creates an IAM admin user to manage IAM resources via the AWS Management Console.
- Configures the AWS CLI using access keys for the admin user.
- Creates an additional IAM user and a `devops` IAM group using AWS CLI commands.
- Generates and applies a customer-managed S3 full-access policy from a JSON document.
- Creates an IAM role with a trust policy that allows Amazon EC2 to assume the role.

## Skills and concepts

- AWS IAM: users, groups, managed policies, customer-managed policies, roles, trust policies.
- AWS CLI: creating and listing IAM resources using commands.
- JSON policy documents for permissions and trust relationships.
- Basic security practices: avoiding committing secrets and real account identifiers.

## Prerequisites

- AWS account.
- An IAM user with permissions to manage IAM (e.g., `IAMFullAccess` or equivalent).
- AWS CLI installed and configured on your local machine.
- Basic understanding of IAM concepts.

## Repository structure

- `README.md` – Project overview and usage instructions.
- `policies/s3full.json` – Example customer-managed S3 full-access policy.
- `policies/trust.json` – Example trust policy that allows EC2 to assume a role.
- `scripts/iam-setup-commands.md` – AWS CLI commands used to create users, groups, policies, and roles.

## How to use

1. Configure AWS CLI with an IAM user that has permission to manage IAM: `aws configure`

2. Create an IAM user and group using the commands in `scripts/iam-setup-commands.md`.

3. Create the S3 full-access policy using `policies/s3full.json` as the policy document.

4. Create the IAM role for EC2 using `policies/trust.json` as the trust policy document.

5. Verify the created resources with the provided list commands.

## Security note

- Do not commit access keys, secret keys, or real account IDs to version control.
- Replace placeholder account IDs and ARNs in the example JSON files with your own values when running the commands.

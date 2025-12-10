# IAM Setup Commands (AWS CLI)

> Replace placeholder value `123456789012` with your own account number.

#### 1. Configure AWS CLI for admin user: 
`aws configure`

Follow prompts for AWS Access Key ID, Secret Access Key, Region, and output format

#### 2. Create IAM user (admin for IAM operations):
`aws iam create-user --user-name iam-admin`

Attach an appropriate policy (for example, IAMFullAccess or a custom admin policy) via console or CLI as per your security model.

#### 3. Create an additional IAM user:
`aws iam create-user --user-name ram`

List users to verify:
`aws iam list-users`

#### 4. Create IAM group:
`aws iam create-group --group-name devops`

List groups to verify:
`aws iam list-groups`

#### 5. Create customer-managed S3 full-access policy:
`aws iam create-policy
--policy-name MyS3Full
--policy-document file://policies/s3full.json`

List customer-managed policies in the account:
`aws iam list-policies --scope Local`

#### 6. Create IAM role for EC2 using trust policy:
`aws iam create-role
--role-name MyEC2Role
--assume-role-policy-document file://policies/trust.json`

List roles to verify:
`aws iam list-roles`

#### 7. (Optional) Attach S3 policy to role or group
Attach to role:
`aws iam attach-role-policy
--role-name MyEC2Role
--policy-arn arn:aws:iam::123456789012:policy/MyS3Full`

Attach to group:
`aws iam attach-group-policy
--group-name devops
--policy-arn arn:aws:iam::123456789012:policy/MyS3Full`

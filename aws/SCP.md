### Service Control Policies (SCPs) in AWS

**Service Control Policies (SCPs)** are a key feature of AWS Organizations that allow you to centrally control permissions for the accounts in your organization. SCPs help you ensure that your accounts stay within the compliance and security boundaries set by your organization.

#### Key Characteristics of SCPs:

1. **Centralized Control**: SCPs are managed from a central location in the AWS Organizations management account. This centralized control allows for consistent policy application across all member accounts.

2. **Permission Boundaries**: SCPs define the maximum permissions that member accounts can have. They do not grant permissions themselves but instead limit the permissions that can be granted by the identity-based policies (like IAM policies) within the accounts.

3. **Policy Inheritance**: SCPs are applied at the organization root, organizational unit (OU), or individual account level. Policies applied at higher levels (like the root) are inherited by all lower levels (OUs and accounts).

4. **Explicit Deny and Allow**: SCPs can explicitly deny or allow specific AWS services or actions. If an action is not allowed by an SCP, even if an IAM policy in the account grants it, the action will be blocked.

#### How SCPs Work:

- **Attached to Entities**: SCPs are attached to the root, OUs, or individual accounts in the organization. When attached, they affect all users and roles within those entities.
- **Default Behavior**: By default, AWS accounts can perform any actions allowed by their IAM policies. When an SCP is applied, it can restrict these actions.
- **Effect on Permissions**: SCPs apply to all users and roles within an account, including the root user. They do not apply to the management account of the organization.

#### Example Use Cases:

1. **Restricting Services**: You can use SCPs to prevent member accounts from using certain AWS services that are not compliant with your organization's policies.
   - Example: Prevent the use of AWS Lambda in all accounts.
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Deny",
           "Action": "lambda:*",
           "Resource": "*"
         }
       ]
     }
     ```

2. **Enforcing Compliance**: SCPs can ensure that all member accounts comply with organizational security and operational policies.
   - Example: Require that all actions must be performed in a specific AWS region.
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Deny",
           "Action": "*",
           "Resource": "*",
           "Condition": {
             "StringNotEquals": {
               "aws:RequestedRegion": "us-west-2"
             }
           }
         }
       ]
     }
     ```

3. **Limiting Resource Creation**: You can restrict the creation of certain types of resources.
   - Example: Prevent the creation of EC2 instances with a specific instance type.
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Deny",
           "Action": "ec2:RunInstances",
           "Resource": "*",
           "Condition": {
             "StringEquals": {
               "ec2:InstanceType": "t2.micro"
             }
           }
         }
       ]
     }
     ```

### Best Practices:

1. **Start with Least Privilege**: Begin with restrictive SCPs and gradually allow more permissions as needed.
2. **Test SCPs**: Test SCPs in a staging environment before applying them to production to avoid unintended disruptions.
3. **Document Policies**: Keep detailed documentation of all SCPs and their purposes for compliance and auditing purposes.
4. **Regular Review**: Periodically review and update SCPs to ensure they align with current organizational policies and requirements.

SCPs are a powerful tool for maintaining governance and compliance across your AWS environment, ensuring that all actions adhere to your organization's security and operational standards.
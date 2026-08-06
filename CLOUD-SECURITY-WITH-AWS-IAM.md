<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://nextwork.ai/projects/aws-security-iam)

**Author:** Gabrielle G. Jalmasco  
**Email:** jalmascogab002@gmail.com

---

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to effectively manage cloud security using AWS Identity and Access Management (IAM) by creating and configuring users, roles, and policies to control access to AWS resources such as EC2 instances. I am doing this project to learn best practices in securing cloud environments, including implementing the principle of least privilege and role-based access control, which will enhance my ability to protect and manage AWS accounts securely.


### Tools and concepts

In this project, the key services I used were Amazon EC2 for managing production and development instances, and AWS Identity and Access Management (IAM) for creating policies, users, and user groups. I applied resource tagging to control access and set up an account alias for easier AWS console login. The key concepts I learnt include how IAM policies define permissions through Effect, Action, and Resource attributes, the use of conditions to restrict access based on tags, the principle of least privilege to limit intern access to development resources only, group-based permission management for centralized control, and the importance of testing permissions by logging in as different IAM users to verify access rights.

### Project reflection

This project took me approximately one hour to complete. The most challenging part was correctly crafting the IAM policy condition to ensure it only applied to the development instances and troubleshooting permission errors when access was denied unexpectedly. It was most rewarding to successfully create a policy and user group that allowed the intern to manage the development instance while preventing any access to the production instance, demonstrating effective and secure permission management.

---

## Tags

### What I did in this step

In this step, I will launch EC2 instances because setting up these virtual servers is the foundation for creating a development environment where applications can run, and it allows me to later configure access controls and security policies to manage who can interact with these instances.

### Understanding tags

Tags are metadata labels consisting of key-value pairs that you can assign to AWS resources such as EC2 instances, IAM users, or policies. They are useful for organizing, identifying, and managing resources by grouping them according to categories like environment (e.g., development, production), project, owner, or cost center. Tags help simplify resource tracking, cost allocation, automation, and access control by enabling you to filter and manage resources efficiently across your AWS account.

### My tag configuration

The tag I’ve used on my EC2 instances is called "Env". The values I’ve assigned for my instances are "production" for the production instance and "development" for the development instance.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step, I will create an IAM policy that grants access to the development EC2 instance because this policy is essential to securely define and control which users or roles can interact with the instance, ensuring proper permissions are in place to protect the environment while enabling necessary access for development tasks.

### Understanding IAM policies

IAM Policies are documents that define permissions by specifying which actions are allowed or denied on specific AWS resources, enabling precise control over user and service access within an AWS account to ensure security and proper resource management.

### The policy I set up

For this project, I’ve set up a policy using the visual editor because it simplifies the process of creating and customizing permissions through an intuitive interface without requiring manual JSON coding.

### Policy effect

I’ve created a policy that grants specific permissions to access and manage the development EC2 instance, allowing authorized users to perform necessary actions while restricting access to other resources for security.

### Understanding Effect, Action, and Resource

The Effect attribute in a JSON policy specifies whether the policy allows or denies the specified actions. The Action attribute defines the specific operations or API calls that are permitted or denied. The Resource attribute identifies the AWS resources to which the policy applies, such as particular EC2 instances or S3 buckets. Together, these attributes control what actions can be performed on which resources and whether those actions are allowed or denied.

---

## My JSON Policy

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, I will create an AWS account alias because it provides a simple, memorable URL for users to log in to the AWS Management Console, making it easier for the intern and other team members to access the AWS account securely and conveniently.

### Understanding account aliases

An account alias is a custom, user-friendly name that replaces the default AWS account ID in the AWS Management Console sign-in URL, making it easier to remember and share the login link with team members.

### Setting up my account alias

Creating an account alias took me just a few minutes.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will create a dedicated IAM group for all NextWork interns and set up an individual IAM user for the new intern because this approach allows me to manage permissions centrally for all interns through the group while providing the intern with a secure, unique login that restricts their access only to the development resources, protecting the production environment from unauthorized access.

### Understanding user groups

IAM user groups are collections of IAM users that allow you to manage permissions for multiple users collectively. Instead of assigning permissions individually to each user, you attach policies to a group, and all users within that group inherit those permissions, simplifying access management and ensuring consistent permission settings.

### Attaching policies to user groups

I attached the policy I created to this user group, which means all users in the group automatically receive the permissions defined in that policy. This ensures that every intern in the group has the same controlled access to the development resources without needing to configure permissions for each user separately.

### Understanding IAM users

IAM users are individual identities created within an AWS account that represent people or applications needing access to AWS resources. Each IAM user has unique credentials and permissions that define what actions they can perform and which resources they can access.

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is to share the AWS Management Console sign-in URL along with the user’s username and temporary password so they can log in and set up their own credentials. The second way is to provide programmatic access credentials (access key ID and secret access key) if the user needs to interact with AWS services via APIs or command-line tools.

### Observations from the IAM user dashboard

Once I logged in as my IAM user, I noticed a limited AWS Management Console dashboard showing only the services and resources I had permissions for. This was because the IAM policy attached to my user or group restricted access to only the development instance and related services, hiding or disabling access to other resources like the production environment.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will test my intern’s access by logging in with their IAM user credentials to verify that they can successfully access the development EC2 instance but are restricted from accessing the production instance. This is important to ensure that the permissions and policies set up in previous steps are correctly enforced, maintaining security while enabling appropriate access.

### Testing policy actions

I tested my JSON IAM policy by attempting to stop both the production and development EC2 instances to verify that the policy correctly allowed stopping the development instance while denying access to the production instance.

### Stopping the production instance

When I tried to stop the production instance, I was denied permission and could not perform the action. This was because the IAM policy explicitly restricted access to the production instance, ensuring that the intern user cannot interfere with critical production resources

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance, the action was successful. This was because the IAM policy granted the necessary permissions to manage the development instance, allowing the intern user to perform required tasks without risking production resources.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

### Understanding the IAM Policy Simulator

### How I used the simulator

---

---

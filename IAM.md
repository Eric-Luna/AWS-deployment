# IAM

Identity and access management helps in ensuring that the right users have appropriate access to the aws resources.

If you are a employer with a root access to AWS and want to allow your employees to have access to the AWS resources, you shouldn't give away your root account mail id and password, instead you should use your account to create User Group and Users from IAM. You can then have control over what your employee can have access to from here.

### User:

> An AWS Identity and Access Management (IAM) user is an entity that you create in AWS to represent the person or application that uses it to interact with AWS. A user in AWS consists of a name and credentials.
From the docs: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_users.html

To add a new user:

IAM console -> User (left nav panel) -> Add user

1. Create a username check on the access type you want. If you are using from application to access resources you might want to go with "Access key - Programmatic access". Programmatic access provides you with access key and secret key. If you simply want your employee to have access to resources you might wan to go with "Password - AWS Management Console access". You can also choose to check on both the check boxes(programmatic access and aws management console access). Now click next.
2. You can choose to add users to group(discussed below). If you don't have any group you can create group or skip this and add it later. click next
3. You can choose to add key-value such as users email for example key would be Email and value would be person@mail.com etc. You can also choose to skip this. Click on next.
4. Now review your choice and click on create.

### User Group:

> An IAM user group is a collection of IAM users. User groups let you specify permissions for multiple users, which can make it easier to manage the permissions for those users.
from the docs: https://docs.aws.amazon.com/IAM/latest/UserGuide/id_groups.html

You can create a security group by heading to IAM console -> User groups(left nav panel) -> Create group.

1. Now give it a group name for example: Database access.

2. add users to the group all the users in this group will have access to resources you specify in attach permisson policy for eg: all users in this group will have acceess to database resources.

3. Attach permission policy by simply clicking on the check-boxs. You can check on multiple checkboxes. For example you can check on "AmazonS3FullAccess" to allow users of this group to have full access to S3 resources.

4. Click on create group.
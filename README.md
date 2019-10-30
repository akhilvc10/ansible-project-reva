# Ansible to create VPC, Subnets, EC2 Instance and RDS
Setting up AWS infrastructure with a Ubuntu server and RDS within its dedicated VPC and associated elements.

# Objectives
In this repository you will be carrying out following tasks in automated way.

-  Create a new VPC
-  Create VPC Subnets
-  Create VPC Routes
-  Create Security Groups
-  Create EC2 Instance
-  Create RDS Instance
-  Clean-up to terminate all above

# Prerequisites
You must have following before running this playbook.
 * AWS Account
 * AWS IAM Security Key and credentials
 * AWS EC2 Key Pair
 * A Linux computer or instance with Ansible, Git, Boto and required Python tools installed.
 * pip install ansible botocore boto3 boto
 * This repository
 
# How to

 * Create a new EC2 Key Pair and secure the private key & add it to .ssh. folder.
   + ``` ssh-add ~/.ssh/{ PrivateKey }.pem ```
 * Download repository using `git clone URL` command.
 * Amend variables listed in `group_vars/all/vars` and add your settings or preferences.
 * Setup Environment Variables
    + ```export AWS_ACCESS_KEY_ID= {aws_access_key_without_double_column}```
    +  ```export SECRET_ACCESS_KEY= {aws_access_key_without_double_column}```
         ( This is for temporary storing the keys )
 * To provision infrastructure run 
   + `ansible-playbook automate.yml`.
 * To clean-up and terminiate your infrastructure you can run `ansible-playbook destroy.yml`.


# Things to consider when changing the region

You need to edit the vars file and change the region

  ## Uploading an existing public key to AWS EC2

 * Use this command ```ssh-keygen -y -f ~/.ssh/ansible-user.pem```
 * After this copy the public key from the output and upload add it and give keypair a name at the end of the key that you entered.
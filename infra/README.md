# Terraform Practice

This project is aiming to practice using Terraform / Ansible

Project will consist of:

* Dependency script to install dependencies on the control node, expected to be Ubuntu-22.04
* A set of Terraform scripts to create:
    * one VM on an AWS account
    * a configuration file containing connection details of the VM
* An Ansible script that installs a LAMP stack on the machine, allows public access to port 80, and runs some tests against the endpoints. This script uses the Terraform output for installation information (e.g. IPs).
* A GitHub Runner script that wraps up the whole process
* A GitHub Runner script that tears down the infrastructure

Configuring AWS credentials for use by Terraform:
The AWS CLI v2 should be installed and on the system path. The AWS_PROFILE environment variable should also be set to the profile defined in ~/.aws/config file, which would look like this:

<pre>
 cat ~/.aws/config
[profile myprofile8]
sso_session = ssoname
sso_account_id = aws_account_id
sso_role_name = rolename
region = eu-west-2
[sso-session timsmithdev]
sso_start_url = https://my-org-start-url
sso_region = eu-west-2
sso_registration_scopes = sso:account:access
</pre>

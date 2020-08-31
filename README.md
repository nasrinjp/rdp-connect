# EC2-connect
You can log in to Windows Server or Linux Server EC2 instances without password.

## Prerequisites

### Environment
This script is available in the following versions.  
  
* PowerShell PSVersion 5
* AWS Tools for PowerShell Version 4

### Settings
You need to set the following parameters to SSM Parameter store.

* Set the password or SSH key for the username.
    * For example, /credentials/ad/\<domain\>/\<username\>
    * For example, /credentials/local/\<Name tag\>/\<username\>
    * For example, /credentials/ssh-key/\<username\>
* Set the IP address you want to login.
    * For example, /ip-address/\<Name tag\>

## Usage

```
# For Windows Server
.\rdp-connect.ps1 -ServerName <name_tag_value> -User <username> -ProfileName <aws_profile_name> -Token <MFA_token_for_aws_profile>

# For Linux Server
.\ssh-connect.ps1 -ServerName <name_tag_value> -User <username> -ProfileName <aws_profile_name> -Token <MFA_token_for_aws_profile>
```

# havingFunAWS

# Description

EC2 Instance setup using strictly AWS Free Tier specifications

OS: Amazon Linux x86
Size: 8G

# Access Setup 
- Add my /32 IP as Security Group
- PEM File (downloaded during setup process) - chmod 400

* ensure Ping to ec2 instance IP

Login Cmd:

```bin/bash
ssh -i <path_to_pem file> ec2-user@<ip>
```

## Server Setup

```bin/bash
sudo yum update
sudo yum install git 

# VENV setup (I'm sure ill need it)
python3 -m venv <venv_name>
source <venv_name>/bin/activate
pip3 install --upgrade pip
pip3 install docker
pip3 install ansible

uptime # just to see how long servers shows up

# Fix timezone
date
timedatectl # Both command will show date/time
ls -l /etc/localtime
timedatectl list-timezones # Get proper timezone name
sudo timedatectl set-timezone <timezone> # Set Timezone
# Example
sudo timedatectl set-timezone America/Chicago

```

Generating New SSH Key:
ssh-keygen -t ed25519 -C "<email>"


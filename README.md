# havingFunAWS

# Description

EC2 Instance strictly using AWS Free Tier specifications

- OS: Amazon Linux x86
- Size: 8G

# Access Setup 
- From AWS Console: Added my /32 IP as Security Rule
- Change PEM File permisions (downloaded during setup process) - 

```bin/bash
# From File Location
chmod 400 <path_to_PEM_file>
``` 

Test Reachability: 
* ensure Ping to ec2 instance IP


Login Cmd:

```bin/bash
ssh -i <path_to_pem file> ec2-user@<ip>
```

## Server Setup

```bin/bash
sudo yum update
sudo yum install git 

# VENV setup
python3 -m venv <venv_name>
source <venv_name>/bin/activate
pip3 install --upgrade pip
pip3 install docker
pip3 install ansible

uptime # just to see how long servers shows up

# Fix timezone

date || or || timedatectl

# Get proper timezone name
timedatectl list-timezones

# Set Timezone
sudo timedatectl set-timezone <timezone>

# Example
sudo timedatectl set-timezone America/Chicago
```

Generating New SSH Key:
```bin/bash
ssh-keygen -t ed25519 -C "<email>"
```

Copying Local SSH Keys to EC2 Instance:
```bin/bash
ssh-agent bash -c "ssh-add <path_to_PEM_file; ssh-copy-id -i ec2-user@<ip>"
```

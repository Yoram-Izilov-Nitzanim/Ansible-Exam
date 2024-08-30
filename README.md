![ANSIBLE_-_AWS_EC2_tags](https://github.com/user-attachments/assets/15fd26de-184b-4423-87f9-daf7444799b5)

# Usage
This project connects your aws with your ansible through tags,<br>
you can install services and sceduale reboots of your instances!

# Pre-installation
![image](https://github.com/user-attachments/assets/a69e4ada-2189-479d-80bb-4316d158f3a4)

# Notes
- You will need your pem key, ansible.cfg, working_after_exam.yaml
- Don't forget to update your path to private key in ansible.cnf
- Change the managed tag in both aws instance tags and inside of the working_after_exam.yaml file - line 11
- Configure your aws cli with keys and region (us-east-1)

Example of tags:<br>

Name yoram-ansible-2<br>
Managed True:Yoram<br>
Service mysql-server<br>
Version 8.0.39-0ubuntu0.24.04.2<br>
Restart */30 * * * *<br>

# Run
```bash
ansible-playbook working_after_exam.yaml
```

# Credits
### Yoram Izilov

# Copy & Paste 
```bash
sudo apt update
sudo apt install -y software-properties-common
sudo apt install -y ansible
ansible-galaxy collection install amazon.aws
sudo apt install -y python3 python3-pip
sudo apt-get install python3-boto3
sudo apt install curl unzip
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws configure
```

# Old guide
```sh
sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
sudo apt install -y python3-pip
sudo apt install -y python3 python3-venv python3-pip
python3 -m venv ~/myenv
source ~/myenv/bin/activate
pip install boto3 botocore
pip install ansible
ansible-galaxy collection install amazon.aws
sudo apt install curl unzip
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws configure # add keys and region
```
IMPORTANT! dont forget to change pem key path in ansible cfg

################################################################################
########################### UPDATED GUIDE - WORKS V1 ###########################
################################################################################
installation without python env:
# note1: you will need your pem key, ansible.cfg, working_after_exam.yaml
# note2: dont forget to update your path to private key in ansible.cnf
# note3: change the managed tag to your liking in both aws instance tags and inside of the working_after_exam.yaml file line 11
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
aws configure # add keys and region
# now just run the playbook - this yaml assumes that your tags are configured correctly 
ansible-playbook working_after_exam.yaml
CONGRATS!
example of tags:
Name yoram-ansible-2
Managed True:Yoram
Restart */30 * * * *
Service
mysql-server
Version
8.0.39-0ubuntu0.24.04.2

##################################################################
########################### OLD GUIDE  ###########################
##################################################################
# Ansible-Exam
step by step installation:

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

IMPORTANT! dont forget to change pem key path in ansible cfg

# Ansible-Exam
step by step installation:

sudo apt update
sudo apt install -y software-properties-common
sudo add-apt-repository --yes --update ppa:ansible/ansible
sudo apt install -y ansible
sudo apt install -y python3-pip
pip3 install boto3 botocore
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
ansible-galaxy collection install amazon.aws

# dont forget to change pem key path in ansible cnf

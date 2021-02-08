### Terraform Installation ####

`apt-get install wget unzip -y`{{execute}}

`wget https://releases.hashicorp.com/terraform/0.14.5/terraform_0.14.5_linux_amd64.zip`{{execute}}

`unzip terraform_0.14.5_linux_amd64.zip`{{execute}}

`mv terraform /usr/local/bin/`{{execute}}

`which terraform`{{execute}}

`terraform -v`{{execute}}


#### Script ###

cat <<EOF > prereq.sh
#!/bin/bash
### Terraform Installation ####
apt-get install wget unzip -y
wget https://releases.hashicorp.com/terraform/0.14.5/terraform_0.14.5_linux_amd64.zip
unzip terraform_0.14.5_linux_amd64.zip
mv terraform /usr/local/bin/
which terraform
terraform -v

### Terraform clone ###
cd /root/
git clone https://github.com/Nagendran2807/terraform-tutorial.git terraform-session
cd terraform-session
ls -lrt

### Local stack ###
docker pull localstack/localstack-light:latest
cd /root/terraform-session/docker
docker-compose up -d

apt-get update -y
apt-get install awscli -y
aws --version

aws configure set profile.localstack.aws_access_key_id test
aws configure set profile.localstack.aws_secret_access_key test
aws configure set profile.localstack.region us-east-1

EOF

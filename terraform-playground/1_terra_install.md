### Terraform Installation ####

`apt-get install wget unzip -y`{{execute}}

`wget https://releases.hashicorp.com/terraform/0.14.5/terraform_0.14.5_linux_amd64.zip`{{execute}}

`unzip terraform_0.14.5_linux_amd64.zip`{{execute}}

`mv terraform /usr/local/bin/`{{execute}}

`which terraform`{{execute}}

`terraform -v`{{execute}}


#### AWS Local stack setup ##########
`docker pull localstack/localstack-light:latest`{{execute}}

`docker images`{{execute}}

`cd /root/terraform-session/docker`{{execute}}

when you setup localstack in ubuntu, use below cmd
`docker-compose up -d`{{execute}}

when you setup localstack in mac, use below cmd
`TMPDIR=/private$TMPDIR docker-compose up -d`{{execute}}

Verify the localstack up and running
`curl http://localhost:4566`{{execute}}


#### AWS setup to communicate aws resources ##########
`apt-get update -y`{{execute}}

`apt-get install awscli -y`{{execute}}

`which aws`{{execute}}

`aws --version`{{execute}}

`aws configure --profile aws`{{execute}}

Enter Access Key & Secret Key

Enter region as us-east-1

Output format is json


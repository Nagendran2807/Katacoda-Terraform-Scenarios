### Terraform Clone ####

Clone our example repository that contains the set of documentation with the following command:

`git clone https://github.com/Nagendran2807/terraform-tutorial.git terraform-session`{{execute}}

Within the repository, you will see a set of examples of implementing various terraform functionality.

`cd terraform-session`{{execute}}

`ls -lrt`{{execute}}


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

## aws profile setup for localstack ###
`apt-get update -y`{{execute}}

`apt-get install awscli -y`{{execute}}

`which aws`{{execute}}

`aws --version`{{execute}}

aws configure set aws_access_key_id test --profile local (or)

`aws configure set profile.local.aws_access_key_id test`{{execute}}

`aws configure set profile.local.aws_secret_access_key test`{{execute}}

`aws configure set profile.local.region us-east-1`{{execute}}

`aws configure list-profiles`{{execute}}

`export AWS_PROFILE=localstack`{{execute}}


#### AWS setup to communicate real aws resources ##########
`apt-get update -y`{{execute}}

`apt-get install awscli -y`{{execute}}

`which aws`{{execute}}

`aws --version`{{execute}}

`aws configure --profile aws-test`{{execute}}

Enter Access Key & Secret Key

Enter region as us-east-1

Output format is json

`export AWS_PROFILE=aws-test`{{execute}}
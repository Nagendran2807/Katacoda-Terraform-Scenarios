### Terraform Data resource ####

`cd /root/terraform-session/data-import`{{execute}}

`pwd`{{execute}}

`terraform init`{{execute}}

`terraform plan`{{execute}}

`terraform apply`{{execute}}



#### Terraform Import AWS #########

Create ec2 instance using cf template

Use below commands, when deal with real AWS resources

`aws cloudformation create-stack --template-body file:///root/terraform-session/ec2sample.json --stack-name single-instance --parameters ParameterKey=InstanceTypeParameter,ParameterValue=t2.micro`{{execute}}

`aws cloudformation list-stacks`{{execute}}

`aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,Tags[?Key==`Name`].Value[0],State.Name,PrivateIpAddress,PublicIpAddress]' --output text`{{execute}}



#### Terraform Import Localstack #########

Use below commands, when deal with Localstack
`aws ec2 run-instances --image-id=ami-07dd19a7900a1f049 --count 1 --instance-type t2.micro  --endpoint-url=http://localhost:4566`{{execute}}

`aws ec2 describe-instances --query 'Reservations[*].Instances[*].[InstanceId,Tags[?Key==`Name`].Value[0],State.Name,PrivateIpAddress,PublicIpAddress]' --output text --endpoint-url=http://localhost:4566`{{execute}}

`cd /root/terraform-session/data-import-localstack`{{execute}}

`pwd`{{execute}}

`terraform init`{{execute}}

put respective instance id here
terraform import aws_instance.webnew i-944e00ef886a0c927

`terraform plan`{{execute}}

`terraform apply`{{execute}}

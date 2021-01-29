### Terraform Installation ####
`apt-get update -y`{{execute}}

`apt-get install wget unzip -y`{{execute}}

`cd /opt/{{execute}}`

`wget https://releases.hashicorp.com/terraform/0.14.5/terraform_0.14.5_linux_amd64.zip`{{execute}}

`unzip terraform_0.14.5_linux_amd64.zip`{{execute}}

`mv terraform /usr/local/bin/`{{execute}}

`which terraform`{{execute}}

`terraform -v`{{execute}}

`cd -`{{execute}}
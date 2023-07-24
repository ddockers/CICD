# Terraform

## What is Terraform?
- Infrastructure as code tool
- Lets you build, change, and version cloud and on-prem resources safely and efficiently
- You can define the end-state and Terraform will figure out how to execute it

## Benefits of Terraform
- Can manage infrastructure on multiple cloud platforms
- Terraform uses a human-readable configuration language HCL (HashiCorp Configuration Language) that simplifies writing infrastructure code
- It tracks resource changes and allows for easy rollback to previous configurations
- It's open source

## Installation of Terraform
<https://spacelift.io/blog/how-to-install-terraform>

A zip folder is downloaded. Unzip the folder to C:.

Add a path to the folder in *Environment Variables*.

![Terraform env var instructions](https://i.imgur.com/GzUosBm.png)

Run `terraform --version` to make sure it's installed.

![Terraform installation](https://i.imgur.com/XIezyhx.png)

## Launching an instance using Terraform

An environment variable needs to be set using the AWS access key. Before, a *system variable* was set. Now, a *user variable* needs to be set.

![Env variable](https://i.imgur.com/jeybPMF.png)

In GitBash, use `mkdir terraform-tech241` to create a directory and `cd` into it.

Create a document called `main.tf` - this is where we'll write the code to launch an instance.

```
# launch an ec2

# which cloud provider? -AWS

# terraform to download required dependencies

# terraform init

# provider name
provider "aws" {
       # which part of thie AWS
       region = "eu-west-1"
}
```
Run `terraform init`.

![Imgur](https://i.imgur.com/avBPboB.png)

Reopen `main.tf`.

```
# launch an ec2

# which cloud provider? -AWS

# terraform to download required dependencies

# terrafitm init

# provider name
provider "aws" {
       # which part of thie AWS
       region = "eu-west-1"
}
# Launch EC2 in Ireland
resource "aws_instance" "app_instance" {

# Which machine/OS version - AMI-id ubuntu 18.04
  ami = "ami-0943382e114f188e8"

# What type of instance (t2 micro)
  instance_type = "t2.micro"

# Is the public IP required
  associate_public_ip_address = true

# Give it a name (tech241-deanne-terraform-app)
  tags = {
       Name = "tech241-deanne-terraform-app"
  }

}
```
Run `terraform plan`.

![Terraform plan output](https://i.imgur.com/sxXgbDv.png)

Run `terraform apply`

![Terraform apply output](https://i.imgur.com/yuGVVGp.png)

**An EC2 instance has been created in AWS!**

To destroy it, run `terraform destroy`.
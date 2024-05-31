# My-Terraform-aws-networking-project
This repo contains a Terraform config file to manage and automate an AWS cloud infrastructure. .

My goal is to;
create a VPC , 
Create an internet gateway, 
Create custom route table, 
Create a subnet, 
Associate subnet to route table, 
Create security groups to allow ports 22,80, (may be 443? - if i can do it without an elastic ip),
Create a network interface with an ip in the subnet created earlier (step 4 - on line 8), 
Assign elastic ip to network interface (or not),
Provision a linux server (install apache2 + user-data).
user data 
  user_data = <<-EOF
              #!/bin/bash
              sudo dnf update -y
              sudo dnf install apache2 -y
              sudo systemctl start apache2
              sudo bash -c "echo my first automated terraform web server" >> /var/www/html/index.html
              EOF

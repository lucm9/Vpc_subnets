# Simple VPC Project

In this project we will will build a secure infrastructure inside AWS VPC (Virtual Private Cloud) network. 

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/d5520ea9-45af-4c76-a0aa-f796356974a2)

Set Up a Virtual Private Network (VPC) Always make reference to the architectural diagram and ensure that your configuration is aligned with it.

- Create a VPC
- Create subnets as shown in the architecture
- Create a route table and associate it with public subnets
- Create a route table and associate it with private subnets
- Create an Internet Gateway
- Edit a route in public route table, and associate it with the Internet Gateway. (This is what allows a public subnet to be accisble from the Internet)
- Create nacl and associate it with public subnets
- Create nacl and associate it with private subnets
## VPC

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/91dfb89f-0e78-4a79-97d0-8e6aee51440e)

## Subnets 

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/8baeb474-b6fc-4152-899f-39d5831bad86)

## Route tables

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/a1ee46a3-d2d1-40b9-88c3-db5c63d7366e)

Open public route table to have connection with the internet

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/d5c9e38c-6ed3-4cc1-9222-ee9a58e42c03)

## Internet Gateway
Create internet gateway and attach gateway to the VPC
![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/9543bad8-e1c4-43fd-8f45-4fc98644aa2a)

## VPC Resource Map

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/0880c3d4-0aee-4e56-aec1-c1c4ffb7e600)

## EC2 Instance

Its time to configure our bastion host in the public subnet and webserver in the private subnet

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/810eafae-3a05-4aa8-9dd8-2e637d698106)

Ensure the EC2 in the private subnet allows ssh from the public VM. We do that by allowing inbound connection from the SG.

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/b36a0219-a82a-410f-88fa-5ccf6e8a5c71)

Ensure the server we are connecting from has the private key on the server. 

![Screenshot 2024-02-14 125250](https://github.com/lucm9/Vpc_subnets/assets/96879757/8d00ff12-6b18-4e16-9b62-c45722123441)

Permission was denied we need to modify permission on the `key-file` as it is deemed to open.

`sudo chmod 400 filename` 

![image](https://github.com/lucm9/Vpc_subnets/assets/96879757/e75be00a-a023-4541-ab95-670cbfb4f982)











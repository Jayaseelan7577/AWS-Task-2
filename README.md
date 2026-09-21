# AWS Task - 2

## Objective

Set up an AWS VPC with an Internet Gateway, create a public subnet with a /24 IPv4 CIDR block, configure routing to the Internet Gateway, and launch a Linux EC2 instance using the public subnet.

## Technologies Used

- AWS VPC
- AWS Internet Gateway
- AWS Subnet
- AWS Route Table
- AWS EC2
- Ubuntu Linux

## VPC Configuration

- VPC Name: AWS-Task-2-VPC
- VPC CIDR: 10.0.0.0/16

## Internet Gateway

- Name: AWS-Task-2-IGW
- Attached to AWS-Task-2-VPC

## Public Subnet

- Subnet Name: AWS-Task-2-Public-Subnet
- CIDR: 10.0.1.0/24
- Availability Zone: ap-south-1b

The /24 subnet provides 256 IPv4 addresses, with 251 available for AWS resources after AWS-reserved addresses.

## Route Table

- Route Table: AWS-Task-2-Public-RT
- Local route: 10.0.0.0/16
- Internet route: 0.0.0.0/0 through AWS-Task-2-IGW
- Public subnet associated with the route table

## EC2 Instance

- Name: AWS-Task-2-Linux
- Instance Type: t3.micro
- Private IP: 10.0.1.38
- Public IPv4: 16.4.23.227
- Subnet: AWS-Task-2-Public-Subnet

## Internet Connectivity Test

The EC2 instance successfully verified internet connectivity using the following command:

curl -s -o /dev/null -w "HTTP Status: %{http_code}\n" https://example.com

Result: HTTP Status: 200

## Result

The AWS VPC, Internet Gateway, public subnet, route table, and Linux EC2 instance were successfully configured. The EC2 instance was launched in the public subnet and successfully accessed the internet.

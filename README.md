# AWS-VPC-Subnetting-Lab
# AWS VPC Design & Subnetting Lab 🚀

## Overview
This lab demonstrates a secure and scalable AWS VPC architecture using industry best practices.

Key objectives:
- Design and deploy a custom VPC.
- Create and configure public and private subnets across two Availability Zones.
- Attach Internet Gateway (IGW) for public resources.
- Deploy a NAT Gateway for secure outbound internet from private subnets.
- Implement custom route tables for proper routing control.
- Configure Security Groups and SSH key pairs securely.
- Validate network paths using EC2 instances as test points.

## Architecture diagram
<img width="1536" height="1024" alt="image" src="https://github.com/user-attachments/assets/dd8d395a-17fb-4fdd-9abb-361507ee160a" />

## Architecture details:
- VPC CIDR: `10.0.0.0/16`
- Public Subnets:
  - `10.0.1.0/24` (AZ-a)
  - `10.0.2.0/24` (AZ-b)
- Private Subnets:
  - `10.0.3.0/24` (AZ-a)
  - `10.0.4.0/24` (AZ-b)
- Internet Gateway attached for public resources.
- NAT Gateway configured and tested for private subnet outbound access (cleaned up to control costs).
- Custom Route Tables for public and private routing rules.
- SSH Bastion (Jump Host) implemented for secure access to private subnet resources.

## Verification steps:
- SSH from my local machine into Public-Test-Instance.
- SSH from Public-Test-Instance into Private-Test-Instance (jump box pattern).
- Tested outbound internet access from both instances:
  - Public-Test-Instance: direct internet access.
  - Private-Test-Instance: NAT Gateway internet access (no inbound exposure).

## Skills practiced:
- AWS VPC design fundamentals
- Subnetting and CIDR block planning
- Internet Gateway vs NAT Gateway
- Route table customization
- Bastion host architecture
- Secure SSH key management and Security Group configuration
- Cost management best practices (cleaned up NAT Gateway, stopped instances)

## Notes:
- All resources cleaned up to avoid unnecessary charges:
  - EC2 instances stopped.
  - NAT Gateway deleted.
  - Elastic IPs released.

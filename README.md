# AWS VPC Peering Architecture

A student cloud-infrastructure project demonstrating two isolated Amazon VPCs connected through VPC Peering, with public subnets, Internet Gateways, route tables, and routes.

## Architecture

- **VPC A** — CIDR `10.0.0.0/16`, public subnet `10.0.1.0/24`
- **VPC B** — CIDR `10.1.0.0/16`, public subnet `10.1.1.0/24`
- One Internet Gateway and public route table per VPC
- A VPC Peering Connection between the two VPCs
- Routes in both VPC route tables to reach the opposite VPC through peering

## Files

- `student-vpc-peering.yaml` — AWS CloudFormation template.

## Deploy using AWS CloudFormation

1. Sign in to the AWS Console and select a Region.
2. Open **CloudFormation** → **Create stack** → **With new resources (standard)**.
3. Upload `student-vpc-peering.yaml`.
4. Enter a stack name and select an Availability Zone supported in your selected Region.
5. Review the parameters and create the stack.
6. Wait for **CREATE_COMPLETE**, then inspect **Outputs** and **Resources**.

## Important notes

- This template creates AWS resources that may incur charges. Check current pricing and delete the stack when finished.
- Public subnets and Internet Gateways are included, but no EC2 instances are launched.
- VPC Peering is not transitive. Communication also requires suitable security-group and network ACL rules.
- This repository contains infrastructure-as-code and deployment instructions. **Deployment is not claimed as completed**; only report deployment after CloudFormation confirms `CREATE_COMPLETE`.

## Cleanup

In CloudFormation, select the stack and choose **Delete** to remove the resources created by this template.

## Author

Ujjwal Anand

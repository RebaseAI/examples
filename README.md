# Examples 

This repository contains practical examples and tutorials demonstrating how to use [Rebase](https://rebase.run) to automate DevOps workflows using AI. Rebase is an AI Native platform that let's you automate your DevOps workflows using plain english (or any other language).

## Purpose

The goal of this repository is to provide real-world examples and step-by-step guides for common DevOps tasks that can be accomplished using Rebase. These examples serve as:

- **Learning resources** for teams new to Rebase
- **Reference guides** for common patterns
- **Templates** for similar projects
- **Documentation** of best practices and workflows

## Getting Started with Rebase

Before diving into the examples, you can [try Rebase for free](https://rebase.run) - no credit card required. Rebase allows you to:

- Provision cloud resources using natural language
- Manage provisoned resources
- Get cost estimates before deployment
- Avoid manual console configuration
- Ensure security best practices

## Examples

### Networking

#### [1. Setup VPC with Public and Private Subnets, IGW and NGW in multiple AZs](./networking/Setup%20VPC%20with%20Public%20and%20Private%20Subnets%2C%20IGW%20and%20NGW%20in%20multiple%20AZs.md)
A detailed tutorial for creating a production-ready VPC architecture including:
- Multi-AZ deployment strategy
- Public subnets for web servers
- Private subnets for databases and sensitive resources
- Internet Gateway (IGW) for public internet access
- NAT Gateway (NGW) for private subnet internet access
- Proper routing configuration
- Cost estimation and optimization

#### [2. Setup VPC Peering](./networking/Setup%20VPC%20Peering.md)
A comprehensive guide showing how to connect multiple VPCs using VPC peering. This example covers:
- Creating multiple VPCs with non-overlapping CIDR blocks
- Setting up private subnets across different VPCs
- Configuring VPC peering connections
- Updating route tables for inter-VPC communication
- Testing connectivity between EC2 instances
- Using AWS SSM for secure instance access

#### [3. Find and Release Unassociated Elastic IPs](./networking/Find%20and%20release%20unassociated%20ElasticIPs.md)
A practical guide for cost optimization by cleaning up unused AWS resources. This example demonstrates:
- Identifying unassociated Elastic IPs across regions
- Understanding the cost implications of unused Elastic IPs
- Using natural language prompts to automate cleanup
- Verifying the cleanup process in AWS Console
- Best practices for ongoing cost management

## Contributing

We love contributions! If you have additional examples or improvements to existing ones, please:

1. Create a new markdown file in the appropriate directory
2. Follow the existing format and structure
3. Include screenshots and step-by-step instructions
4. Add a link to your example in this README

## Structure

```
examples/
├── networking/          # Network infrastructure use cases
│   ├── Setup VPC Peering.md
│   ├── Setup VPC with Public and Private Subnets, IGW and NGW in multiple AZs.md
│   └── Find and release unassociated ElasticIPs.md
└── README.md           # This file
```

## More Resources

- [Rebase Documentation](https://docs.rebase.run)
- [Rebase Blog](https://blog.rebase.run)
- [Rebase Website](https://rebase.run/)

## Join Our Community

We would love for you to join our organization at [dev.to](https://dev.to/rebase-ai/) to stay updated with the latest DevOps automation tips, tutorials, and community discussions. We're always excited to see interesting use cases and workflows that you create with Rebase! Feel free to shoot us an email at m@rebase.run to get an invite.

---

*This repository is maintained by the Rebase team. For questions or support, visit [rebase.run](https://rebase.run).* 
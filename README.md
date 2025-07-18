# Examples Repository

This repository contains practical examples and tutorials demonstrating how to use [Rebase](https://rebase.run) to simplify DevOps infrastructure deployment and management. Rebase is an AI-powered platform that allows you to provision and manage cloud resources through natural language commands, eliminating the need for complex manual configuration.

## Purpose

The goal of this repository is to provide real-world examples and step-by-step guides for common DevOps infrastructure tasks that can be accomplished using Rebase. These examples serve as:

- **Learning resources** for teams new to Rebase
- **Reference guides** for common infrastructure patterns
- **Templates** for similar projects
- **Documentation** of best practices and workflows

## Getting Started with Rebase

Before diving into the examples, you can [try Rebase for free](https://rebase.run) - no credit card required. Rebase allows you to:

- Provision cloud resources using natural language
- Get cost estimates before deployment
- Manage infrastructure with AI assistance
- Avoid manual console configuration
- Ensure security best practices

## Examples

### Networking

#### [Setup VPC Peering](./networking/Setup%20VPC%20Peering.md)
A comprehensive guide showing how to connect multiple VPCs using VPC peering. This example covers:
- Creating multiple VPCs with non-overlapping CIDR blocks
- Setting up private subnets across different VPCs
- Configuring VPC peering connections
- Updating route tables for inter-VPC communication
- Testing connectivity between EC2 instances
- Using AWS SSM for secure instance access

#### [Setup VPC with Public and Private Subnets, IGW and NGW in multiple AZs](./networking/Setup%20VPC%20with%20Public%20and%20Private%20Subnets%2C%20IGW%20and%20NGW%20in%20multiple%20AZs.md)
A detailed tutorial for creating a production-ready VPC architecture including:
- Multi-AZ deployment strategy
- Public subnets for web servers
- Private subnets for databases and sensitive resources
- Internet Gateway (IGW) for public internet access
- NAT Gateway (NGW) for private subnet internet access
- Proper routing configuration
- Cost estimation and optimization

## Contributing

We welcome contributions! If you have additional examples or improvements to existing ones, please:

1. Create a new markdown file in the appropriate directory
2. Follow the existing format and structure
3. Include screenshots and step-by-step instructions
4. Add a link to your example in this README

## Structure

```
use_cases/
├── networking/          # Network infrastructure use cases
│   ├── Setup VPC Peering.md
│   └── Setup VPC with Public and Private Subnets, IGW and NGW in multiple AZs.md
└── README.md           # This file
```

## More Resources

- [Rebase Documentation](https://docs.rebase.run)
- [Rebase Blog](https://blog.rebase.run)
- [Rebase Website](https://rebase.run/)

---

*This repository is maintained by the Rebase team. For questions or support, visit [rebase.run](https://rebase.run).* 
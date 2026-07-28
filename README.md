# Architecture

## Network Design
- **VNet**: 10.0.0.0/16
- **Subnets**: BastionSubnet /24, AppSubnet /24, DBSubnet /24
- **Isolation**: NSGs on each subnet

## Security
- **Access**: Azure Bastion only. No RDP/SSH public
- **Secrets**: Key Vault with Private Endpoint
- **Data**: Storage with Private Endpoint + Private DNS

## Compute
- **VMs**: Deployed in AppSubnet, no public IP
- **Load Balancing**: Internal Load Balancer with TCP health probe port 80

## Why Bicep Modules?
Reusability. Same module for dev and prod. Prevents drift.

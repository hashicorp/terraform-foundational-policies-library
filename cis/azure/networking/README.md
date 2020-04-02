#  CIS Microsoft Azure Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Microsoft Azure Foundations Benchmark version 1.1.0](https://www.cisecurity.org/benchmark/azure/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 6.1: Ensure that RDP access is restricted from the internet

### Overview
The potential security problem with using RDP over the Internet is that attackers can use various brute force techniques to gain access to Azure Virtual Machines. This policy evaluates whether RDP access is disabled from the Internet.

### Configuration

```hcl
policy "azure-cis-6.1-networking-deny-public-rdp-nsg-rules" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/networking/azure-cis-6.1-networking-deny-public-rdp-nsg-rules/azure-cis-6.1-networking-deny-public-rdp-nsg-rules.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 6.2: Ensure that SSH access is restricted from the internet

### Overview
The potential security problem with using SSH over the Internet is that attackers can use various brute force techniques to gain access to Azure Virtual Machines. This policy evaluates whether SSH access is disabled from the Internet.

### Configuration

```hcl
policy "azure-cis-6.2-networking-deny-public-ssh-nsg-rules" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/networking/azure-cis-6.2-networking-deny-public-ssh-nsg-rules/azure-cis-6.2-networking-deny-public-ssh-nsg-rules.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 6.3: Ensure no SQL Databases allow ingress 0.0.0.0/0 (ANY IP)

### Overview
By default, for a SQL server, a Firewall exists with StartIp of 0.0.0.0 and EndIP of 0.0.0.0 allowing access to all the Azure services. In order to reduce the potential attack surface for a SQL server, firewall rules should be defined with more granular IP addresses by referencing the range of addresses available from specific datacenters.

### Configuration

```hcl
policy "azure-cis-6.3-networking-deny-any-sql-database-ingress" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/networking/azure-cis-6.3-networking-deny-any-sql-database-ingress/azure-cis-6.3-networking-deny-any-sql-database-ingress.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 6.4: Ensure that Network Security Group Flow Log retention period is 'greater than 90 days'

### Overview
Flow logs enable capturing information about IP traffic flowing in and out of network security groups. Logs can be used to check for anomalies and give insight into suspected breaches.

### Configuration

```hcl
policy "azure-cis-6.4-networking-enforce-network-watcher-flow-log-retention-period" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/networking/azure-cis-6.4-networking-enforce-network-watcher-flow-log-retention-period/azure-cis-6.4-networking-enforce-network-watcher-flow-log-retention-period.sentinel"
  enforcement_level = "advisory"
}
```

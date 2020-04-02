#  CIS Microsoft Azure Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Microsoft Azure Foundations Benchmark version 1.1.0](https://www.cisecurity.org/benchmark/azure/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 4.11: Ensure 'Enforce SSL connection' is set to 'ENABLED' for MySQL Database Server

### Overview
Enforcing SSL connections between database server and client applications helps protect against "man in the middle" attacks by encrypting the data stream between the server and application.

### Configuration

```hcl
policy "azure-cis-4.11-databases-mysql-enforce-ssl-connection-is-enabled" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/databases/azure-cis-4.11-databases-mysql-enforce-ssl-connection-is-enabled/azure-cis-4.11-databases-mysql-enforce-ssl-connection-is-enabled.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 4.13: Ensure 'Enforce SSL connection' is set to 'ENABLED' for PostgreSQL Database Server

### Overview
Enforcing SSL connections between database server and client applications helps protect against "man in the middle" attacks by encrypting the data stream between the server and application.

### Configuration

```hcl
policy "azure-cis-4.13-databases-psql-enforce-ssl-connection-is-enabled" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/databases/azure-cis-4.13-databases-psql-enforce-ssl-connection-is-enabled/azure-cis-4.13-databases-psql-enforce-ssl-connection-is-enabled.sentinel"
  enforcement_level = "advisory"
}
```

#  CIS Microsoft Azure Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Microsoft Azure Foundations Benchmark version 1.1.0](https://www.cisecurity.org/benchmark/azure/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 3.1: Ensure that 'Secure transfer required' is set to 'Enabled'

### Description
The secure transfer option enhances the security of a storage account by only allowing requests to the storage account by a secure connection.

### Configuration

```hcl
policy "azure-cis-3.1-storage-secure-transfer-required-is-enabled" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/storage/azure-cis-3.1-storage-secure-transfer-required-is-enabled/azure-cis-3.1-storage-secure-transfer-required-is-enabled.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.3: Ensure Storage logging is enabled for Queue service for read, write, and delete requests

### Description
Storage Analytics logs contain detailed information about successful and failed requests to a storage service. This information can be used to monitor individual requests and to diagnose issues with a storage service.

### Configuration

```hcl
policy "azure-cis-3.3-storage-queue-logging-is-enabled" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/storage/azure-cis-3.3-storage-queue-logging-is-enabled/azure-cis-3.3-storage-queue-logging-is-enabled.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.6: Ensure that 'Public access level' is set to Private for blob containers

### Description
It is recommended not to provide anonymous access to blob containers until, and unless, it is strongly desired. A shared access signature token should be used for providing controlled and timed access to blob containers.

### Configuration

```hcl
policy "azure-cis-3.6-storage-blob-public-access-level-set-to-private" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/storage/azure-cis-3.6-storage-blob-public-access-level-set-to-private/azure-cis-3.6-storage-blob-public-access-level-set-to-private.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.7: Ensure default network access rule for Storage Accounts is set to deny

### Description
Storage accounts should be configured to deny access to traffic from all networks (including internet traffic). Access can be granted to traffic from specific Azure Virtual networks, allowing a secure network boundary for specific applications to be built. Access can also be granted to public internet IP address ranges, to enable connections from specific internet or on-premises clients.

### Configuration

```hcl
policy "azure-cis-3.7-storage-default-network-access-rule-set-to-deny" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/storage/azure-cis-3.7-storage-default-network-access-rule-set-to-deny/azure-cis-3.7-storage-default-network-access-rule-set-to-deny.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.8: Ensure 'Trusted Microsoft Services' is enabled for Storage Account access

### Description
Turning on firewall rules for storage account will block access to incoming requests for data, including from other Azure services. You can get access to services like Monitor, Networking, Hubs, and Event Grid by enabling "Trusted Microsoft Services" through exceptions.

### Configuration

```hcl
policy "azure-cis-3.8-storage-trusted-microsoft-services-is-enabled" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/storage/azure-cis-3.8-storage-trusted-microsoft-services-is-enabled/azure-cis-3.8-storage-trusted-microsoft-services-is-enabled.sentinel"
  enforcement_level = "advisory"
}
```

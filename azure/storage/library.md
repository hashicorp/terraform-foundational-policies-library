#  CIS Microsoft Azure Foundational Sentinel policies

## CIS 3.1: Ensure that 'Secure transfer required' is set to 'Enabled'

```hcl
policy "azure-cis-3.1-storage-secure-transfer-required-is-enabled.sentinel" {
  source     = "github.com/hashicorp/azure/storage/azure-cis-3.1-storage-secure-transfer-required-is-enabled/azure-cis-3.1-storage-secure-transfer-required-is-enabled.sentinel?ref=master"
  enforce    = "advisory"
}
```

## CIS 3.3: Ensure Storage logging is enabled for Queue service for read, write, and delete requests

```hcl
policy "azure-cis-3.3-storage-queue-logging-is-enabled.sentinel" {
  source     = "github.com/hashicorp/azure/storage/azure-cis-3.3-storage-queue-logging-is-enabled/azure-cis-3.3-storage-queue-logging-is-enabled.sentinel?ref=master"
  enforce    = "advisory"
}
```

## CIS 3.6: Ensure that 'Public access level' is set to Private for blob containers

```hcl
policy "azure-cis-3.6-storage-blob-public-access-level-set-to-private" {
  source     = "github.com/hashicorp/azure/storage/azure-cis-3.6-storage-blob-public-access-level-set-to-private/azure-cis-3.6-storage-blob-public-access-level-set-to-private.sentinel?ref=master"
  enforce    = "advisory"
}
```

## CIS 3.7: Ensure default network access rule for Storage Accounts is set to deny

```hcl
policy "azure-cis-3.7-storage-default-network-access-rule-set-to-deny" {
  source     = "github.com/hashicorp/azure/storage/azure-cis-3.7-storage-default-network-access-rule-set-to-deny/azure-cis-3.7-storage-default-network-access-rule-set-to-deny.sentinel?ref=master"
  enforce    = "advisory"
}
```

## CIS 3.8: Ensure 'Trusted Microsoft Services' is enabled for Storage Account access

```hcl
policy "azure-cis-3.8-storage-trusted-microsoft-services-is-enabled" {
  source     = "github.com/hashicorp/azure/storage/azure-cis-3.8-storage-trusted-microsoft-services-is-enabled/azure-cis-3.8-storage-trusted-microsoft-services-is-enabled.sentinel?ref=master"
  enforce    = "advisory"
}
```
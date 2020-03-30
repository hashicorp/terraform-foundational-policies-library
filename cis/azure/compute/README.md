#  CIS Microsoft Azure Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Microsoft Azure Foundations Benchmark version 1.1.0](https://www.cisecurity.org/benchmark/azure/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 7.1: Ensure that all managed disks (OS and Data) are encrypted

### Overview
Encrypting the VM's OS and data disks ensures that all content is fully unrecoverable without a key and thus protects the volumes from unwarranted reads.

### Configuration

```hcl
policy "azure-cis-7.1-compute-managed-disk-encryption-is-enabled" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/compute/azure-cis-7.1-compute-managed-disk-encryption-is-enabled/azure-cis-7.1-compute-managed-disk-encryption-is-enabled.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 7.4: Ensure that only approved extensions are installed

### Overview
Azure virtual machine extensions are small applications that run with administrative privileges on Azure virtual machines. These extensions could potentially access anything on a virtual machine and therefore only approved extensions should be used within an organizations Azure subscriptions.

### Configuration

```hcl
policy "azure-cis-7.4-compute-only-approved-extensions-are-installed" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/azure/compute/azure-cis-7.4-compute-only-approved-extensions-are-installed/azure-cis-7.4-compute-only-approved-extensions-are-installed.sentinel"
  enforcement_level = "advisory"
}
```

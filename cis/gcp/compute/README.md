#  CIS Google Cloud Computing Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Google Cloud Computing Platform Foundations Benchmark v.1.0.0](https://www.cisecurity.org/benchmark/google_cloud_computing_platform/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 4.2: Ensure "Block Project-wide SSH keys" enabled for VM instances

### Description
Project-wide SSH keys are stored in Compute/Project-meta-data. Project wide SSH keys can be used to login into all the instances within project. Using project-wide SSH keys eases the SSH key management but if compromised, poses the security risk which can impact all the instances within project. It is recommended to use Instance specific SSH keys which can limit the attack surface if the SSH keys are compromised.

### Configuration

```hcl
policy "gcp-cis-4.2-compute-block-project-wide-ssh-keys-enabled-for-vm-instances" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/compute/gcp-cis-4.2-compute-block-project-wide-ssh-keys-enabled-for-vm-instances/gcp-cis-4.2-compute-block-project-wide-ssh-keys-enabled-for-vm-instances.sentinel"
    enforcement_level = "advisory"
}
```
## CIS 4.3: Ensure oslogin is enabled for a Project

### Description
Enabling osLogin ensures that SSH keys used to connect to instances are mapped with IAM users. Revoking access to IAM user will revoke all the SSH keys associated with that particular user. It facilitates centralized and automated SSH key pair management which is useful in handling cases like response to compromised SSH key pairs and/or revocation of external/third-party/Vendor users.

### Configuration

```hcl
policy "gcp-cis-4.3-compute-ensure-oslogin-is-enabled-for-a-project" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/compute/gcp-cis-4.3-compute-ensure-oslogin-is-enabled-for-a-project/gcp-cis-4.3-compute-ensure-oslogin-is-enabled-for-a-project.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 4.4: Ensure 'Enable connecting to serial ports' is not enabled for VM Instance

### Description
If you enable the interactive serial console on an instance, clients can attempt to connect to that instance from any IP address. Therefore interactive serial console support should be disabled.

### Configuration
```hcl
policy "gcp-cis-4.4-compute-enable-connecting-to-serial-ports-is-not-enabled-for-vm-instance" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/compute/gcp-cis-4.4-compute-enable-connecting-to-serial-ports-is-not-enabled-for-vm-instance/gcp-cis-4.4-compute-enable-connecting-to-serial-ports-is-not-enabled-for-vm-instance.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 4.5: Ensure that IP forwarding is not enabled on Instances

### Description
Compute Engine instance cannot forward a packet unless the source IP address of the packet matches the IP address of the instance. Similarly, GCP won't deliver a packet whose destination IP address is different than the IP address of the instance receiving the packet. However, both capabilities are required if you want to use instances to help route packets. Forwarding of data packets should be disabled to prevent data loss or information disclosure.

### Configuration

```hcl
policy "gcp-cis-4.5-compute-ensure-that-ip-forwarding-is-not-enabled-on-instances" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/compute/gcp-cis-4.5-compute-ensure-that-ip-forwarding-is-not-enabled-on-instances/gcp-cis-4.5-compute-ensure-that-ip-forwarding-is-not-enabled-on-instances.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 4.6: Ensure VM disks for critical VMs are encrypted with Customer- Supplied Encryption Keys (CSEK)

### Description
If you provide your own encryption keys, Compute Engine uses your key to protect the Google-generated keys used to encrypt and decrypt your data. Only users who can provide the correct key can use resources protected by a customer-supplied encryption key. Google does not store your keys on its servers and cannot access your protected data unless you provide the key.

> **Note:**
If you forget or lose your key, there is no way for Google to recover the key or to recover any data encrypted with the lost key.

### Configuration

```hcl
policy "gcp-cis-4.6-compute-ensure-vm-disks-for-critical-vms-are-encrypted-with-customer-supplied-encryption-keys" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/compute/gcp-cis-4.6-compute-ensure-vm-disks-for-critical-vms-are-encrypted-with-customer-supplied-encryption-keys/gcp-cis-4.6-compute-ensure-vm-disks-for-critical-vms-are-encrypted-with-customer-supplied-encryption-keys.sentinel"
    enforcement_level = "advisory"
}
```
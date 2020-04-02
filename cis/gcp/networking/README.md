#  CIS Google Cloud Computing Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Google Cloud Computing Platform Foundations Benchmark v.1.0.0](https://www.cisecurity.org/benchmark/google_cloud_computing_platform/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 3.1: Ensure the default network does not exist in a project

### Description
The default network has automatically created firewall rules and has pre-fabricated network configuration. Based on your security and networking requirements, you should create your network and delete the default network.

### Configuration

```hcl
policy "gcp-cis-3.1-networking-deny-default-network-in-project" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.1-networking-deny-default-network-in-project/gcp-cis-3.1-networking-deny-default-network-in-project.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.3: Ensure that DNSSEC is enabled for Cloud DNS

### Description
Domain Name System Security Extensions (DNSSEC) adds security to the Domain Name System (DNS) protocol by enabling DNS responses to be validated.

### Configuration

```hcl
policy "gcp-cis-3.3-networking-dnssec-is-enabled-for-cloud-dns" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.3-networking-dnssec-is-enabled-for-cloud-dns/gcp-cis-3.3-networking-dnssec-is-enabled-for-cloud-dns.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.4: Ensure that RSASHA1 is not used for key-signing key in Cloud DNS DNSSEC

### Description
DNSSEC algorithm numbers in this registry may be used in CERT RRs. Zone signing (DNSSEC) and transaction security mechanisms (SIG(0) and TSIG) make use of particular subsets of these algorithms. The algorithm used for key signing should be recommended one and it should not be weak.

### Configuration

```hcl
policy "gcp-cis-3.4-networking-dnssec-rsasha1-is-not-key-signing-key" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.4-networking-dnssec-rsasha1-is-not-key-signing-key/gcp-cis-3.4-networking-dnssec-rsasha1-is-not-key-signing-key.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.5: Ensure that RSASHA1 is not used for zone-signing key in Cloud DNS DNSSEC

### Description
DNSSEC algorithm numbers in this registry may be used in CERT RRs. Zone signing (DNSSEC) and transaction security mechanisms (SIG(0) and TSIG) make use of particular subsets of these algorithms. The algorithm used for key signing should be recommended one and it should not be weak.

### Configuration

```hcl
policy "gcp-cis-3.5-networking-dnssec-rsasha1-is-not-used-for-zone-signing-key" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.5-networking-dnssec-rsasha1-is-not-used-for-zone-signing-key/gcp-cis-3.5-networking-dnssec-rsasha1-is-not-used-for-zone-signing-key.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.6: Ensure that SSH access is restricted from the internet

### Description
To avoid the most general (0.0.0.0/0) destination IP Range specified from the Internet through SSH with a default Port 22, we need to restrict generic access from Internet to specific IP Range.

### Configuration

```hcl
policy "gcp-cis-3.6-networking-ssh-is-restricted-from-internet" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.6-networking-ssh-is-restricted-from-internet/gcp-cis-3.6-networking-ssh-is-restricted-from-internet.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.7: Ensure that RDP access is restricted from the internet

### Description
To avoid the most general (0.0.0.0/0) destination IP Range specified from the Internet through RDP with a default Port 3389, we need to restrict generic access from Internet to specific IP Range.

### Configuration

```hcl
policy "gcp-cis-3.7-networking-rdp-is-restricted-from-internet" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.7-networking-rdp-is-restricted-from-internet/gcp-cis-3.7-networking-rdp-is-restricted-from-internet.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.8: Ensure Private Google Access is enabled for all subnetwork in VPC Network

### Description
VPC networks and subnetworks provide logically isolated and secure network partitions where you can launch GCP resources. When Private Google Access is enabled, VM instances in a subnet can reach the Google Cloud and Developer APIs and services without needing an external IP address.

### Configuration

```hcl
policy "gcp-cis-3.8-networking-private-google-access-is-enabled-for-all-vpc-subnets" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.8-networking-private-google-access-is-enabled-for-all-vpc-subnets/gcp-cis-3.8-networking-private-google-access-is-enabled-for-all-vpc-subnets.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 3.9: Ensure VPC Flow logs is enabled for every subnet in VPC Network

### Description
VPC networks and subnetworks provide logically isolated and secure network partitions where you can launch GCP resources. When Flow Logs is enabled for a subnet, VMs within subnet starts reporting on all TCP and UDP flows.

### Configuration

```hcl
policy "gcp-cis-3.9-networking-vpc-flow-logs-is-enabled-for-all-vpc-subnets" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/networking/gcp-cis-3.9-networking-vpc-flow-logs-is-enabled-for-all-vpc-subnets/gcp-cis-3.9-networking-vpc-flow-logs-is-enabled-for-all-vpc-subnets.sentinel"
  enforcement_level = "advisory"
}
```
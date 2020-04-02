#  CIS Amazon Web Services Foundational Sentinel policies
The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Amazon Web Services Foundations Benchmark version 1.2.0](https://www.cisecurity.org/benchmark/amazon_web_services/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 4.1: Ensure no security groups allow ingress from 0.0.0.0/0 to port 22

### Description
Removing unfettered connectivity to remote console services, such as SSH, reduces a server's exposure to risk.

### Configuration

```hcl
policy "aws-cis-4.1-networking-deny-public-ssh-acl-rules" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/aws/networking/aws-cis-4.1-networking-deny-public-ssh-acl-rules/aws-cis-4.1-networking-deny-public-ssh-acl-rules.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 4.2: Ensure no security groups allow ingress from 0.0.0.0/0 to port 3389

### Description
Removing unfettered connectivity to remote console services, such as RDP, reduces a server's exposure to risk.

### Configuration

```hcl
policy "aws-cis-4.2-networking-deny-public-rdp-acl-rules" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/aws/networking/aws-cis-4.2-networking-deny-public-rdp-acl-rules/aws-cis-4.2-networking-deny-public-rdp-acl-rules.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 4.3: Ensure the default security group of every VPC restricts all traffic

### Description
Configuring all VPC default security groups to restrict all traffic will encourage least privilege security group development and mindful placement of AWS resources into security groups which will in-turn reduce the exposure of those resources.

### Configuration

```hcl
policy "aws-cis-4.3-networking-restrict-all-vpc-traffic-acl-rules" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/aws/networking/aws-cis-4.3-networking-restrict-all-vpc-traffic-acl-rules/aws-cis-4.3-networking-restrict-all-vpc-traffic-acl-rules.sentinel"
  enforcement_level = "advisory"
}
```

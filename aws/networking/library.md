#  CIS Amazon Web Services Foundational Sentinel policies

## CIS 4.1: Ensure no security groups allow ingress from 0.0.0.0/0 to port 22

```hcl
policy "aws-cis-4.1-networking-deny-public-ssh-acl-rules" {
  source     = "github.com/hashicorp/aws/networking/aws-cis-4.1-networking-deny-public-ssh-acl-rules/aws-cis-4.1-networking-deny-public-ssh-acl-rules.sentinel?ref=master"
  enforce    = "advisory"
}
```

## CIS 4.2: Ensure no security groups allow ingress from 0.0.0.0/0 to port 3389

```hcl
policy "aws-cis-4.2-networking-deny-public-rdp-acl-rules" {
  source     = "github.com/hashicorp/aws/networking/aws-cis-4.2-networking-deny-public-rdp-acl-rules/aws-cis-4.2-networking-deny-public-rdp-acl-rules.sentinel?ref=master"
  enforce    = "advisory"
}
```

## CIS 4.3: Ensure the default security group of every VPC restricts all traffic

```hcl
policy "aws-cis-4.3-networking-restrict-all-vpc-traffic-acl-rules" {
  source     = "github.com/hashicorp/aws/networking/aws-cis-4.3-networking-restrict-all-vpc-traffic-acl-rules/aws-cis-4.3-networking-restrict-all-vpc-traffic-acl-rules.sentinel?ref=master"
  enforce    = "advisory"
}
```
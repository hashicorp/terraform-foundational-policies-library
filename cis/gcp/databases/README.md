#  CIS Google Cloud Computing Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Google Cloud Computing Platform Foundations Benchmark v.1.0.0](https://www.cisecurity.org/benchmark/google_cloud_computing_platform/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 6.1: Ensure that Cloud SQL database instance requires all incoming connections to use SSL

### Description
For security, it is recommended to always use SSL encryption when connecting to your instance. This recommendation is applicable for Postgresql, MySql generation 1 and MySql generation 2 Instances.

### Configuration

```hcl
policy "gcp-cis-6.1-databases-cloud-sql-databases-instance-requires-all-incoming-connections-to-use-ssl" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/databases/gcp-cis-6.1-databases-cloud-sql-databases-instance-requires-all-incoming-connections-to-use-ssl/gcp-cis-6.1-databases-cloud-sql-databases-instance-requires-all-incoming-connections-to-use-ssl.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 6.2: Ensure that Cloud SQL database Instances are not open to the world


### Description
To minimize attack surface on a Database server Instance, only trusted/known and required IP(s) should be white-listed to connect to it.

### Configuration

```hcl
policy "gcp-cis-6.2-databases-cloud-sql-databases-instances-are-not-open-to-the-world" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/databases/gcp-cis-6.2-databases-cloud-sql-databases-instances-are-not-open-to-the-world/gcp-cis-6.2-databases-cloud-sql-databases-instances-are-not-open-to-the-world.sentinel"
    enforcement_level = "advisory"
}
```
#  CIS Google Cloud Computing Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Google Cloud Computing Platform Foundations Benchmark v.1.0.0](https://www.cisecurity.org/benchmark/google_cloud_computing_platform/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 5.1: Ensure that Cloud Storage bucket is not anonymously or publicly accessible

### Description
Allowing anonymous and/or public access grants permissions to anyone to access bucket content. Such access might not be desired if you are storing any sensitive data. Hence, ensure that anonymous and/or public access to a bucket is not allowed.

### Configuration

```hcl
policy "gcp-cis-5.1-storage-deny-anonymous-or-public-bucket-access" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/storage/gcp-cis-5.1-storage-deny-anonymous-or-public-bucket-access/gcp-cis-5.1-storage-deny-anonymous-or-public-bucket-access.sentinel"
  enforcement_level = "advisory"
}
```

## CIS 5.3: Ensure that logging is enabled for Cloud storage buckets

### Description
By enabling access and storage logs on target Storage buckets, it is possible to capture all events which may affect objects within target buckets. Configuring logs to be placed in a separate bucket allows access to log information which can be useful in security and incident response workflows.

### Configuration

```hcl
policy "gcp-cis-5.3-storage-bucket-logging-is-enabled" {
  source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/storage/gcp-cis-5.3-storage-bucket-logging-is-enabled/gcp-cis-5.3-storage-bucket-logging-is-enabled.sentinel"
  enforcement_level = "advisory"
}
```

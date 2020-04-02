#  CIS Google Cloud Computing Foundational Sentinel policies

The following code snippets show the configuration settings that are required to successfully deploy Sentinel policies that follow the security recommendations that are provided in the [CIS Google Cloud Computing Platform Foundations Benchmark v.1.0.0](https://www.cisecurity.org/benchmark/google_cloud_computing_platform/). We cover policy configuration in more details in the [Managing Sentinel Policies](https://www.terraform.io/docs/cloud/sentinel/manage-policies.html) section in the Terraform Cloud [documentation](https://www.terraform.io/docs/cloud/index.html).

## CIS 7.1: Ensure Stackdriver Logging is set to Enabled on Kubernetes Engine Clusters

### Description
Stackdriver Logging is part of the Stackdriver suite of products in Google Cloud Platform. It includes storage for logs, a user interface called the Logs Viewer, and an API to manage logs programmatically. Stackdriver Logging lets you have Kubernetes Engine automatically collect, process, and store your container and system logs in a dedicated, persistent datastore. Container logs are collected from your containers. System logs are collected from the cluster's components, such as docker and kubelet. Events are logs about activity in the cluster, such as the scheduling of Pods.

### Configuration

```hcl
policy "gcp-cis-7.1-kubernetes-ensure-stackdriver-logging-is-set-to-enabled-on-kubernetes-engine-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.1-kubernetes-ensure-stackdriver-logging-is-set-to-enabled-on-kubernetes-engine-clusters/gcp-cis-7.1-kubernetes-ensure-stackdriver-logging-is-set-to-enabled-on-kubernetes-engine-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.2: Ensure Stackdriver Monitoring is set to Enabled on Kubernetes Engine Clusters

### Description
Stackdriver Monitoring to monitor signals and build operations in your Kubernetes Engine clusters. Stackdriver Monitoring can access metrics about CPU utilization, some disk traffic metrics, network traffic, and uptime information. Stackdriver Monitoring uses the Monitoring agent to access additional system resources and application services in virtual machine instances.

### Configuration
```hcl
policy "gcp-cis-7.2-kubernetes-ensure-stackdriver-monitoring-is-set-to-enabled-on-kubernetes-engine-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.2-kubernetes-ensure-stackdriver-monitoring-is-set-to-enabled-on-kubernetes-engine-clusters/gcp-cis-7.2-kubernetes-ensure-stackdriver-monitoring-is-set-to-enabled-on-kubernetes-engine-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.3: Ensure Legacy Authorization is set to Disabled on Kubernetes Engine Clusters

### Description
In Kubernetes, authorizers interact by granting a permission if any authorizer grants the permission. The legacy authorizer in Kubernetes Engine grants broad, statically defined permissions. To ensure that RBAC limits permissions correctly, you must disable the legacy authorizer. RBAC has significant security advantages, can help you ensure that users only have access to cluster resources within their own namespace and is now stable in Kubernetes.

### Configuration
```hcl
policy "gcp-cis-7.3-kubernetes-ensure-legacy-authorization-is-set-to-disabled-on-kubernetes-engine-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.3-kubernetes-ensure-legacy-authorization-is-set-to-disabled-on-kubernetes-engine-clusters/gcp-cis-7.3-kubernetes-ensure-legacy-authorization-is-set-to-disabled-on-kubernetes-engine-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.4: Ensure Master authorized networks is set to Enabled on Kubernetes Engine Clusters

### Description
Authorized networks are a way of specifying a restricted range of IP addresses that are permitted to access your container cluster's Kubernetes master endpoint. Kubernetes Engine uses both Transport Layer Security (TLS) and authentication to provide secure access to your container cluster's Kubernetes master endpoint from the public internet. This provides you the flexibility to administer your cluster from anywhere; however, you might want to further restrict access to a set of IP addresses that you control. You can set this restriction by specifying an authorized network.

### Configuration
```hcl
policy "gcp-cis-7.4-kubernetes-ensure-master-authorized-networks-is-set-to-enabled-on-kubernetes-engine-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.4-kubernetes-ensure-master-authorized-networks-is-set-to-enabled-on-kubernetes-engine-clusters/gcp-cis-7.4-kubernetes-ensure-master-authorized-networks-is-set-to-enabled-on-kubernetes-engine-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.5: Ensure Kubernetes Clusters are configured with Labels

### Description
A cluster label is a key-value pair that helps you organize your Google Cloud Platform resources, such as clusters. You can attach a label to each resource, then filter the resources based on their labels. Information about labels is forwarded to the billing system, so you can break down your billing charges by the label.

### Configuration
```hcl
policy "gcp-cis-7.5-kubernetes-ensure-kubernetes-clusters-are-configured-with-labels" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.5-kubernetes-ensure-kubernetes-clusters-are-configured-with-labels/gcp-cis-7.5-kubernetes-ensure-kubernetes-clusters-are-configured-with-labels.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.7: Ensure Automatic node repair is enabled for Kubernetes Clusters

### Description
Kubernetes Engine's node auto-repair feature helps you keep the nodes in your cluster in a healthy, running state. When enabled, Kubernetes Engine makes periodic checks on the health state of each node in your cluster. If a node fails consecutive health checks over an extended time period, Kubernetes Engine initiates a repair process for that node. If you disable node auto-repair at any time during the repair process, the in-progress repairs are not cancelled and still complete for any node currently under repair.

### Configuration
```hcl
policy "gcp-cis-7.7-kubernetes-ensure-automatic-node-repair-is-enabled-for-kubernetes-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.7-kubernetes-ensure-automatic-node-repair-is-enabled-for-kubernetes-clusters/gcp-cis-7.7-kubernetes-ensure-automatic-node-repair-is-enabled-for-kubernetes-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.8: Ensure Automatic node upgrades is enabled on Kubernetes Engine Clusters nodes

### Description
Node auto-upgrades help you keep the nodes in your cluster or node pool up to date with the latest stable version of Kubernetes. Auto-Upgrades use the same update mechanism as manual node upgrades.

### Configuration
```hcl
policy "gcp-cis-7.8-kubernetes-ensure-automatic-node-upgrades-is-enabled-on-kubernetes-engine-clusters-nodes" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.8-kubernetes-ensure-automatic-node-upgrades-is-enabled-on-kubernetes-engine-clusters-nodes/gcp-cis-7.8-kubernetes-ensure-automatic-node-upgrades-is-enabled-on-kubernetes-engine-clusters-nodes.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.9: Ensure Container-Optimized OS (cos) is used for Kubernetes Engine Clusters Node image

### Description
Container-Optimized OS is an operating system image for your Compute Engine VMs that is optimized for running Docker containers. With Container-Optimized OS, you can bring up your Docker containers on Google Cloud Platform quickly, efficiently, and securely.

### Configuration
```hcl
policy "gcp-cis-7.9-kubernetes-ensure-container-optimized-osis-used-for-kubernetes-engine-clusters-node-image" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.9-kubernetes-ensure-container-optimized-osis-used-for-kubernetes-engine-clusters-node-image/gcp-cis-7.9-kubernetes-ensure-container-optimized-osis-used-for-kubernetes-engine-clusters-node-image.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.10: Ensure Basic Authentication is disabled on Kubernetes Engine Clusters

### Description
Basic authentication allows a user to authenticate to the cluster with a username and password and it is stored in plain text without any encryption. Disabling Basic authentication will prevent attacks like brute force. Its recommended to use either client certificate or IAM for authentication.

### Configuration
```hcl
policy "gcp-cis-7.10-kubernetes-ensure-basic-authentication-is-disabled-on-kubernetes-engine-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.10-kubernetes-ensure-basic-authentication-is-disabled-on-kubernetes-engine-clusters/gcp-cis-7.10-kubernetes-ensure-basic-authentication-is-disabled-on-kubernetes-engine-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.11: Ensure Network policy is enabled on Kubernetes Engine Clusters

### Description
A network policy is a specification of how groups of pods are allowed to communicate with each other and other network endpoints. NetworkPolicy resources use labels to select pods and define rules which specify what traffic is allowed to the selected pods. The Kubernetes Network Policy API allows the cluster administrator to specify what pods are allowed to communicate with each other.

### Configuration
```hcl
policy "gcp-cis-7.11-kubernetes-ensure-network-policy-is-enabled-on-kubernetes-engine-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.11-kubernetes-ensure-network-policy-is-enabled-on-kubernetes-engine-clusters/gcp-cis-7.11-kubernetes-ensure-network-policy-is-enabled-on-kubernetes-engine-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.12: Ensure Kubernetes Cluster is created with Client Certificate enabled

### Description
If you disable client certificate generation to create a cluster without a client certificate. You will still be able to authenticate to the cluster with basic auth or IAM. But basic auth allows a user to authenticate to the cluster with a username and password which are stored in plain text without any encryption and might lead brute force attacks.

### Configuration
```hcl
policy "gcp-cis-7.12-kubernetes-ensure-kubernetes-cluster-is-created-with-client-certificate-enabled" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.12-kubernetes-ensure-kubernetes-cluster-is-created-with-client-certificate-enabled/gcp-cis-7.12-kubernetes-ensure-kubernetes-cluster-is-created-with-client-certificate-enabled.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.13: Ensure Kubernetes Cluster is created with Alias IP ranges enabled

### Description
Google Cloud Platform Alias IP Ranges lets you assign ranges of internal IP addresses as aliases to a virtual machine's network interfaces. This is useful if you have multiple services running on a VM and you want to assign each service a different IP address.

### Configuration
```hcl
policy "gcp-cis-7.13-kubernetes-ensure-kubernetes-cluster-is-created-with-alias-ip-ranges-enabled" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.13-kubernetes-ensure-kubernetes-cluster-is-created-with-alias-ip-ranges-enabled/gcp-cis-7.13-kubernetes-ensure-kubernetes-cluster-is-created-with-alias-ip-ranges-enabled.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.14: Ensure PodSecurityPolicy controller is enabled on the Kubernetes Engine Clusters

### Description
A Pod Security Policy is a cluster-level resource that controls security sensitive aspects of the pod specification. The PodSecurityPolicy objects define a set of conditions that a pod must run with in order to be accepted into the system, as well as defaults for the related fields.

### Configuration
```hcl
policy "gcp-cis-7.14-kubernetes-ensure-podsecuritypolicy-controller-is-enabled-on-the-kubernetes-engine-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.14-kubernetes-ensure-podsecuritypolicy-controller-is-enabled-on-the-kubernetes-engine-clusters/gcp-cis-7.14-kubernetes-ensure-podsecuritypolicy-controller-is-enabled-on-the-kubernetes-engine-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.15: Ensure Kubernetes Cluster is created with Private cluster enabled

### Description
A private cluster is a cluster that makes your master inaccessible from the public internet. In a private cluster, nodes do not have public IP addresses, so your workloads run in an environment that is isolated from the internet. Nodes have addressed only in the private RFC 1918 address space. Nodes and masters communicate with each other privately using VPC peering.

### Configuration
```hcl
policy "gcp-cis-7.15-kubernetes-ensure-kubernetes-cluster-is-created-with-private-cluster-enabled" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.15-kubernetes-ensure-kubernetes-cluster-is-created-with-private-cluster-enabled/gcp-cis-7.15-kubernetes-ensure-kubernetes-cluster-is-created-with-private-cluster-enabled.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.17: Ensure default Service account is not used for Project access in Kubernetes Clusters

### Description
A service account is an identity that an instance or an application can use to run API requests on your behalf. This identity is used to identify applications running on your virtual machine instances to other Google Cloud Platform services. By default, Kubernetes Engine nodes are given the Compute Engine default service account. This account has broad access by default, making it useful to a wide variety of applications, but it has more permissions than are required to run your Kubernetes Engine cluster.

### Configuration
```hcl
policy "gcp-cis-7.17-kubernetes-ensure-default-service-account-is-not-used-for-project-access-in-kubernetes-clusters" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.17-kubernetes-ensure-default-service-account-is-not-used-for-project-access-in-kubernetes-clusters/gcp-cis-7.17-kubernetes-ensure-default-service-account-is-not-used-for-project-access-in-kubernetes-clusters.sentinel"
    enforcement_level = "advisory"
}
```

## CIS 7.18: Ensure Kubernetes Clusters created with limited service account Access scopes for Project access

### Description
Access scopes are the legacy method of specifying permissions for your instance. Before the existence of IAM roles, access scopes were the only mechanism for granting permissions to service accounts. By default, your node service account has access scopes.

### Configuration
```hcl
policy "gcp-cis-7.18-kubernetes-ensure-kubernetes-clusters-created-with-limited-service-account-access-scopes-for-project-access" {
    source = "https://raw.githubusercontent.com/hashicorp/terraform-foundational-policies-library/master/cis/gcp/kubernetes/gcp-cis-7.18-kubernetes-ensure-kubernetes-clusters-created-with-limited-service-account-access-scopes-for-project-access/gcp-cis-7.18-kubernetes-ensure-kubernetes-clusters-created-with-limited-service-account-access-scopes-for-project-access.sentinel"
    enforcement_level = "advisory"
}
```
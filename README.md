# Sentinel Foundational Policies Library

This repository contains a library of Sentinel policies that can be used within Terraform Cloud to accelerate your adoption of policy as code. If you wish to learn more about the Sentinel and framework, please review the Sentinel [documentation](https://docs.hashicorp.com/sentinel/).

---

## Table of Contents
- [Prerequisites](#Prerequisites)
- [Documentation](#documentation)
- [Setup & Integration](#setup-&-integration)
- [Version Control System (VCS)](#version-control-system-(vcs))
- [Policy Set Configuration](#policy-set-configuration)
- [Policy Set Management](#policy-set-management)
- [Policy Guides](#policy-guides)
- [Useful Resources](#useful-resources)

---

## Prerequisites

Before you start adopting some of the policies within this library it is recommended that you do the following:

1. [Install](https://docs.hashicorp.com/sentinel/intro/getting-started/install/) the Sentinel CLI. The CLI is an excellent tool for familiarizing yourself with the internals of Sentinel and allows you to `apply` and `test` policies outside of the Terraform platform. You can find more information related the Sentinel CLI in the [Enforce Policy with Sentinel](https://learn.hashicorp.com/terraform?track=sentinel#sentinel) learning track.

3. Terraform Cloud with the _Governance and Policy Plan_ enabled.
4. Access to a [supported](https://www.terraform.io/docs/cloud/vcs/index.html#supported-vcs-providers) version control system (VCS) provider.

---

## Documentation
The file and directory structure within this repository has been designed to have a descriptive `ROOT` directory that contains all policies that are related to a given standard. As an example, all policies for the Center for Internet Security Benchmarks are all located within the `cis` directory. Policies are then broken down by cloud service provider (i.e. AWS, Azure and GCP) and then categorized by cloud service (i.e. Compute, Databases, Networking etc.)

```
.
└── ROOT
    └── CLOUD
       └── CATEGORY
           └── POLICY
               └── ...
```

All `CATEGORY` related directories contain a single README.md that details all information that is required to assess and enforce a policy in Terraform Cloud. This information includes:
- Policy name
- Description of the controls that are evaluated
- The Policy Set configuration that needs to be added to the `sentinel.hcl` file.

> **Note:** You can find a full list of all available policies in the [Policy Guides](#policy-guides) section.

---
↥ [back to top](#table-of-contents)

## Setup & Integration

Before you can use any of the policies within this library, you will need to configure Terraform Cloud. The following sections detail the high-level steps required to deploy a policy from the foundational policies library. The [Enforce Policy with Sentinel](https://learn.hashicorp.com/terraform?track=sentinel#sentinel) learning track covers the end-to-end process in greater detail. If this is the first time you are setting up a Sentinel policy, we encourage you to familiarize yourself with this track prior to continuing further.

### Version Control System (VCS)
Terraform Cloud provides first-class support for VCS integration. This allows VCS repositories to contain all of the policies and configuration needed to manage Sentinel policy at scale. [Integrating with VCS](https://www.terraform.io/docs/cloud/getting-started/policies.html#integrating-with-vcs) is as simple as:

1. [Connect a VCS Providers to Terraform Cloud](https://www.terraform.io/docs/cloud/vcs/index.html)
2. Create a repository in your VCS provider that will be used as the source of your Policy Set configuration
3. Clone the source repository to a local directory

### Policy Set Configuration

Once your VCS is integrated with Terraform Cloud, you are now ready to configure your Terraform Policy Set. The process for creating a Policy Set is as follows:

1. Identifying a policy from the foundational policies library that you would like to enforce on a Terraform [Workspace](https://www.terraform.io/docs/cloud/workspaces/index.html)
2. Review the README.md documentation and copy the configuration snippet for the policy you have chosen.
3. Create a `sentinel.hcl` configuration file within the local directory for your repository.
4. Edit the contents of the `sentinel.hcl` by pasting the configuration snippet into the body of the configuration file.
5. Committing your changes to your local repository content and then use the `git push` command to upload the changes to your remote repository.


### Policy Set Management

Now that you have configured your Policy Set, it is time to enforce this configuration on a Terraform Cloud workspace. This is achieved by:

1. Browsing to your Terraform Cloud organization settings
2. Browse to Policy Set settings
3. Connect a new Policy Set
4. Connect your VCS
5. Choose your repository
6. Configure your policy settings (i.e. Policy Path, Branch & Workspace Scope)

Now that the Policy Set is configured and ready, navigate to your target workspace and queue a new plan. You should see the policy check phase appear in the run details, and you should see the newly created policy execute and return the state of the policy evaluation (i.e. `Pass` or `Fail`).

---

## Policy Guides

### Center for Internet Security (CIS)
- Amazon Web Services
    - [Networking](cis/aws/networking/README.md)
- Microsoft Azure
    - [Compute](cis/azure/compute/README.md)
    - [Databases](cis/azure/databases/README.md)
    - [Networking](cis/azure/networking/README.md)
    - [Storage](cis/azure/storage/README.md)
- Google Cloud Platform
    - [Compute](cis/gcp/compute/README.md)
    - [Databases](cis/gcp/databases/README.md)
    - [Kubernetes](cis/gcp/kubernetes/README.md)
    - [Networking](cis/gcp/networking/README.md)
    - [Storage](cis/gcp/storage/README.md)

---

↥ [back to top](#table-of-contents)

## Useful Resources
- [Getting Started with Terraform Cloud](https://www.terraform.io/docs/cloud/getting-started/index.html)
- [Configuring Version Control Access](https://www.terraform.io/docs/cloud/getting-started/vcs.html)
- [Configuring Sentinel Policies](https://www.terraform.io/docs/cloud/getting-started/policies.html)
- [Sentinel Overview](https://www.terraform.io/docs/cloud/sentinel/index.html)
- [Example Policies](https://www.terraform.io/docs/cloud/sentinel/examples.html)
- [Sentinel Documentation](https://docs.hashicorp.com/sentinel/)
- [Sentinel Language](https://docs.hashicorp.com/sentinel/language/)
- [Sentinel Language Specification](https://docs.hashicorp.com/sentinel/language/spec/)

---

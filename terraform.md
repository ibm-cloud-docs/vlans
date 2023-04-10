---

copyright:
  years: 2021, 2023
lastupdated: "2023-04-07"

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}


# Setting up Terraform for VLANs
{: #terraform-setup-vlans}

Terraform on {{site.data.keyword.cloud}} enables predictable and consistent provisioning of {{site.data.keyword.cloud_notm}} services so that you can rapidly build complex, multi-tier cloud environments following Infrastructure as Code (IaC) principles. Similar to using the {{site.data.keyword.cloud_notm}} CLI or API and SDKs, you can automate the provisioning, update, and deletion of your VLAN instances by using HashiCorp Configuration Language (HCL).
{: shortdesc}

Looking for a managed Terraform on {{site.data.keyword.cloud}} solution? Try out [{{site.data.keyword.bplong}}](/docs/schematics?topic=schematics-getting-started). With {{site.data.keyword.bpshort}}, you can use the Terraform scripting language that you are familiar with, but you don't have to worry about setting up and maintaining the Terraform command line and the {{site.data.keyword.cloud}} Provider plug-in. {{site.data.keyword.bpshort}} also provides pre-defined Terraform templates that you can easily install from the {{site.data.keyword.cloud}} catalog.
{: tip}

## Installing Terraform and configuring resources for VLANs
{: #install-terraform-vlans}

Before you can create an authorization by using Terraform, make sure that you have completed the following:

* Make sure that you have the [required access](/docs/account?topic=account-mngclassicinfra) to create and work with VLAN resources.
* Install the Terraform CLI and configure the {{site.data.keyword.cloud_notm}} Provider plug-in for Terraform. For more information, see the tutorial for [Getting started with Terraform on {{site.data.keyword.cloud}}](/docs/ibm-cloud-provider-for-terraform?topic=ibm-cloud-provider-for-terraform-getting-started). The plug-in abstracts the {{site.data.keyword.cloud_notm}} APIs that are used to complete this task.
* Create a Terraform configuration file that is named `main.tf`. In this file, you define resources by using HashiCorp Configuration Language. For more information, see the [Terraform documentation](https://www.terraform.io/docs/language/index.html){: external}.

1. Create a Terraform configuration file that is named `main.tf`. In this file, you add the configuration to create a VLAN service instance and to assign a user an access policy in Identity and Access Management (IAM) for that instance by using HashiCorp Configuration Language (HCL). For more information, see the [Terraform documentation](https://www.terraform.io/docs/language/index.html){: external}.

   The VLAN resource in the following example is named `test_vlan`. This `PUBLIC` VLAN resides in the `sjc04` data center and `fcr01a.sjc04` is the hostname of the primary router associated with the VLAN.

      For more information, see the [ibm_network_vlan](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/network_vlan){: external} usage example.
      {: note}

   ```terraform
   resource "ibm_network_vlan" "test_vlan" {
     name            = "test_vlan"
     datacenter      = "sjc04"
     type            = "PUBLIC"
     router_hostname = "fcr01a.sjc04"
     tags = [
       "collectd",
       "mesos-master",
     ]
   }
   ```
   {: codeblock}

1. After you finish building your configuration file, initialize the Terraform CLI. For more information, see [Initializing Working Directories](https://www.terraform.io/cli/init){: external}.

   ```terraform
   terraform init
   ```
   {: pre}

1. Create a Terraform execution plan. The Terraform execution plan summarizes all the actions that need to be run to create the VLAN instance in your account.

   ```terraform
   terraform plan
   ```
   {: pre}

1. Create the VLAN instance in {{site.data.keyword.cloud_notm}}.

   ```terraform
   terraform apply
   ```
   {: pre}

1. From the [{{site.data.keyword.cloud_notm}} resource list](/resources){: external}, select the VLAN instance that you created and note the instance ID.

## What's next?
{: #terraform-setup-next}

Now that you successfully created your VLAN with Terraform on {{site.data.keyword.cloud_notm}}, you can visit the [VLAN Terraform registry](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/network_vlan){: external} to perform additional tasks using Terraform.

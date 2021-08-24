---

copyright:
  years: 2021
lastupdated: "2021-08-12"

subcollection: vlans

---

{:external: target="_blank" .external}
{:shortdesc: .shortdesc}
{:screen: .screen}
{:pre: .pre}
{:note: .note}
{:table: .aria-labeledby="caption"}
{:codeblock: .codeblock}
{:tip: .tip}


# Setting up Terraform for VLANs
{: #terraform-setup-vlans}

Terraform on {{site.data.keyword.cloud}} enables predictable and consistent provisioning of {{site.data.keyword.cloud_notm}} services so that you can rapidly build complex, multi-tier cloud environments following Infrastructure as Code (IaC) principles. Similar to using the {{site.data.keyword.cloud_notm}} CLI or API and SDKs, you can automate the provisioning, update, and deletion of your VLAN instances by using HashiCorp Configuration Language (HCL).
{: shortdesc}

Looking for a managed Terraform on {{site.data.keyword.cloud}} solution? Try out [{{site.data.keyword.bplong}}](/docs/schematics?topic=schematics-getting-started). With {{site.data.keyword.bpshort}}, you can use the Terraform scripting language that you are familiar with, but you don't have to worry about setting up and maintaining the Terraform command line and the {{site.data.keyword.cloud}} Provider plug-in. {{site.data.keyword.bpshort}} also provides pre-defined Terraform templates that you can easily install from the {{site.data.keyword.cloud}} catalog.
{: tip}

## Installing Terraform and configuring resources for VLANs
{: #install-terraform-vlans}

To install Terraform and configure resources for VLANs:

1. Follow the [Terraform on {{site.data.keyword.cloud}} getting started tutorial](/docs/ibm-cloud-provider-for-terraform?topic=ibm-cloud-provider-for-terraform-getting-started) to install the Terraform CLI and configure the {{site.data.keyword.cloud}} Provider plug-in for Terraform. The plug-in abstracts the {{site.data.keyword.cloud}} APIs that are used to provision, update, or delete VLAN service instances and resources.

1. Create a Terraform configuration file that is named `main.tf`. In this file, you add the configuration to create a VLAN service instance. For more information, see the [Terraform documentation](https://www.terraform.io/docs/language/index.html){: external}.

   The VLAN resource in the following example is named `test_vlan`. This `PUBLIC` VLAN resides in the `dal06` data center and `fcr01a.dal06` is the hostname of the primary router associated with the VLAN.

      For more information, see the [ibm_network_vlan](https://registry.terraform.io/providers/IBM-Cloud/ibm/latest/docs/resources/network_vlan){: external} usage example.
      {: note}

   ```terraform
   resource "ibm_network_vlan" "test_vlan" {
     name            = "test_vlan"
     datacenter      = "dal06"
     type            = "PUBLIC"
     router_hostname = "fcr01a.dal06"
     tags = [
       "collectd",
       "mesos-master",
     ]
   }
   ```
   {: codeblock}

3. Initialize the Terraform CLI.

   ```
   terraform init
   ```
   {: pre}

4. Create a Terraform execution plan. The Terraform execution plan summarizes all the actions that need to be run to create the VLAN instance in your account.

   ```
   terraform plan
   ```
   {: pre}

5. Create the VLAN instance in {{site.data.keyword.cloud_notm}}.

   ```
   terraform apply
   ```
   {: pre}

6. From the [{{site.data.keyword.cloud_notm}} resource list](/resources){: external}, select the VLAN instance that you created and note the instance ID.

---
copyright:
  years: 1994, 2019
lastupdated: "2019-11-27"

keywords: compute order, Additional compute orders, Premium VLANs

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}
{:external: target="_blank" .external}
{:DomainName: data-hd-keyref="DomainName"}

# Getting started with VLANs
{: #getting-started}

Virtual Local Area Networks (VLANs) are used by {{site.data.keyword.cloud}} to isolate broadcast traffic on the public and private networks. VLANs are assigned as needed to fulfill other offerings. For instance, if you place a compute order for a data center in which you don't yet have a presence, you automatically receive a VLAN. Additional compute orders for the same data center, which do not specify network requirements, usually are placed in the previously assigned VLAN. All VLANs that are assigned automatically are also removed automatically when your resources no longer require them.

VLANs are specific to the routers used in IBM Cloud data centers, and a data center contains multiple routers for both the public and private networks. Thus, it is possible that multiple VLANs can be assigned within a single data center. It also is possible to order additional VLANs to construct more complex network topologies; typically in conjunction with a [Virtual Router Appliance](/docs/virtual-router-appliance?topic=virtual-router-appliance-getting-started).

We refer to purchased VLANs as **Premium VLANs** and VLANs automatically managed by {{site.data.keyword.cloud}} as **Automatic VLANs**. Learn more about how VLANs operate in [About VLANs](/docs/vlans?topic=vlans-about-vlans).


## Managing VLANs
{:#managing-vlans}

Follow these steps to review the VLANs on your account.

  1. From your browser, open the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/){: external} and log in to your account.
  1. From the dashboard, click the Menu icon ![Menu icon](../../icons/icon_hamburger.svg) and select **Classic Infrastructure**.
  1. Select **Network > IP Management > VLANs**.

The VLANs listing displays information about your VLANs, and it provides access to each VLAN, along with associated devices or subnets.

### Understanding pod versus data center selection
{:#pod-vs-datacenter-selection}

The options for where to order a VLAN provide for different needs and constraints. This section summarizes reasons why you might select one option over another.

The **Order by Pod** option allows you to specify the exact pod (and thus router) where you require a VLAN. Use this option if you have a specific reason for the VLAN to exist in that pod. Reasons for this include using the VLAN with an existing Gateway Appliance or multi-VLAN Firewall. Typically, if you are ordering additional VLANs as part of a larger deployment scheme, you know what pod you want the VLANs in. If so, choose this option.

Use the **Order by data center** option when the location of the VLAN is less important. This option is best when you want to seed a location for which you will cluster other resources. If your deployments follow a network first strategy (as opposed to ordering servers first), using this option to establish your presence in a new data center provides the best experience. Your requested VLANs are fulfilled by any pod in the selected data center; set no expectations about which pod will be selected when choosing this option.

It's best to use the least specific location option available that fits your current need.

### Complex orders
{:#complex-orders-vlans}

The portal ordering experience only provides for ordering a single VLAN configuration per order. A configuration consists of the desired network, location option, and quantity. While it is possible to order multiple VLAN configurations in a single order via the API, each configuration quantity is restricted to 1. This means that each VLAN configuration provided is fulfilled independently. Thus, if each configuration utilizes the data center location option, each VLAN can be assigned to different pods within that data center.

### A note about capacity
{:#note-about-capacity}

An attempt to order a VLAN may be prevented due to capacity restrictions in the location selected. If encountered, it affects all users trying to order VLANs in that location; no recourse is available. If possible, we encourage you to establish a presence in another data center, and consider taking advantage of [VLAN spanning](/docs/vlans?topic=vlans-vlan-spanning). If your location needs are flexible, it's best to use the least specific location option when ordering VLANs, because this allows for greater flexibility in allocating your VLANs. Additionally, VLAN capacity in a previously attempted location can become available at a later time.


## Canceling premium VLANs
{:#canceling-premium-vlans}

When you are ready to remove a premium VLAN, locate that VLAN in your account's VLAN listing (See Managing VLANs) and click the "X" icon within the entry to initiate the cancellation prompts.

Premium VLANs cannot be canceled if they are being used by other products. The following uses prevent cancellation:

  * Servers directly homed on the VLAN (as opposed to trunked).
  * Secondary subnets routed to the VLAN or an IP address on the VLAN.
  * Firewall products which serve the entire VLAN. This excludes non-dedicated hardware firewalls, for instance.
  * Association to an Auto Scale Group.
  * Being trunked to servers (this will change in the future).

Additionally, some products and features **do not prevent cancellation** of a VLAN, but are affected by its removal. These include:

  * Being protected by a Virtual Router Appliance. The VLAN association will be removed whether it is bypassed or not.

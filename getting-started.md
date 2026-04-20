---

copyright:
  years: 1994, 2026

lastupdated: "2026-04-20"

keywords: vlans, vlan

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# Getting started with VLANs
{: #getting-started}

Virtual Local Area Networks (VLANs) are used by {{site.data.keyword.cloud}} to isolate broadcast traffic on the public and private networks.
{: shortdesc}

VLANs are assigned as needed to fulfill other offerings. For instance, if you place a compute order for a data center in which you don't yet have a presence, you automatically receive a VLAN. More compute orders for the same data center, which do not specify network requirements, usually are placed in the previously assigned VLAN. All VLANs that are assigned automatically are also removed automatically when you no longer have the resources that require them.

VLANs are specific to the routers used in {{site.data.keyword.cloud_notm}} data centers, and a data center contains multiple routers for both the public and private networks. Thus, it is possible that multiple VLANs can be assigned within a single data center. It is also possible to order more VLANs to construct more complex network topologies; typically along with a [Virtual Router Appliance](/docs/virtual-router-appliance?topic=virtual-router-appliance-getting-started-vra).

Purchased VLANs are referred to as **Premium VLANs** and VLANs automatically managed by {{site.data.keyword.cloud_notm}} as **Automatic VLANs**. For more information, see [About VLANs](/docs/vlans?topic=vlans-about-vlans).


## Managing VLANs
{: #managing-vlans}

Follow these steps to review the VLANs on your account.

1. From your browser, open the [{{site.data.keyword.cloud_notm}} console](/login) and log in to your account.
1. From the console, click the Navigation Menu icon ![Navigation Menu icon](../../icons/icon_hamburger.svg) and select **Infrastructure > Classic Infrastructure**.
1. Select **Network > IP Management > VLANs**.

The VLANs listing displays information about your VLANs, and it provides access to each VLAN, along with associated devices or subnets.

### Understanding pod versus data center selection
{: #pod-vs-datacenter-selection}

The options for where to order a VLAN provide for different needs and constraints. Review the reasons why you might select one option over another.

The **Order by Pod** option allows you to specify the exact pod (and thus the router) where you require a VLAN. Use this option if you have a specific reason for the VLAN to exist in that pod. Reasons for this include using the VLAN with an existing Gateway Appliance or multi-VLAN Firewall. Typically, if you are ordering additional VLANs as part of a larger deployment scheme, you know what pod you want the VLANs in. If so, choose this option.

Use the **Order by data center** option when the location of the VLAN is less important. This option is best when you want to seed a location for which you will cluster other resources. If your deployments follow a network first strategy (as opposed to ordering servers first), using this option to establish your presence in a new data center provides the best experience. Your requested VLANs are fulfilled by any pod in the selected data center. Set no expectations about which pod is selected when you choose this option.

It's best to use the least specific location option available that fits your current need.

### Complex orders
{: #complex-orders-vlans}

The portal ordering experience provides for ordering only a single VLAN configuration per order. A configuration consists of the wanted network, location option, and quantity. While it is possible to order multiple VLAN configurations in a single order with the API, each configuration quantity is restricted to 1. This means that each VLAN configuration provided is fulfilled independently. Thus, if each configuration uses the data center location option, each VLAN can be assigned to different pods within that data center.

### A note about capacity
{: #note-about-capacity}

An attempt to order a VLAN can be prevented due to capacity restrictions in the location selected. If encountered, it affects all users that try to order VLANs in that location; no recourse is available. If possible, we encourage you to establish a presence in another data center, and consider taking advantage of [VLAN spanning](/docs/vlans?topic=vlans-vlan-spanning). If your location needs are flexible, it's best to use the least specific location option when you order VLANs because this allows for greater flexibility in allocating your VLANs. Also, VLAN capacity in a previously attempted location can become available later.

## Canceling premium VLANs
{: #canceling-premium-vlans}

When you are ready to remove a premium VLAN, locate the VLAN in your account's VLAN listing and click **Cancel VLAN** from the VLAN's Actions menu ![Actions menu](/images/overflow.png).

Premium VLANs cannot be cancelled if they are being used by other products. The following uses prevent cancellation:

* Servers directly homed on the VLAN (as opposed to trunked).
* Firewall products that serve the entire VLAN. This excludes nondedicated hardware firewalls, for instance.

Also, some products and features **do not prevent cancellation** of a VLAN, but are affected by its removal. This includes being protected by a Virtual Router Appliance. The VLAN association is removed whether it is bypassed or not.

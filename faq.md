---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-10-10"

keywords: new VLAN, subnet selector, VLAN moves

subcollection: vlans

---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:generic: data-hd-programlang="generic"}
{:faq: data-hd-content-type='faq'}

# FAQs
{:#vlans-faqs}

## Can I move an existing device to a new VLAN?
{: faq}

Existing compute devices, such as a virtual server instance (VSI) or a bare metal, cannot be moved to a new VLAN. A new VSI or bare metal needs to be provisioned in the new VLAN and deprovisioned accordingly. Single VLAN firewalls cannot be moved to a new VLAN either. Multi VLAN firewalls can be attached to the new VLAN and then detached from the previous VLAN. Refer to the specific offering documentation for capabilities and limitations.


## Is there a way to specify which VLAN I want to use for my device when I order it?
{: faq}

Yes, a specific VLAN may be selected during the ordering process. When ordering a device, this option is available at the end of the order form. A private VLAN is selected, followed by a public VLAN. Also note that a subnet selector is presented for each VLAN; this selection is **optional**. Only select a subnet if you have reason to do so, as selecting a subnet which lacks available IP addresses will negatively impact the fulfillment of the device (See the [Subnet FAQ](/docs/infrastructure/subnets?topic=subnets-faq) for more details).

It is important to note that the selected VLAN must be located in the same datacenter as the device. We cannot assign a device to a VLAN that is in a different datacenter.


## How many devices may be assigned to a single VLAN?
{: faq}

Currently, no limit exists for the number of devices that are associated with a single VLAN at any time; however, when a hardware firewall is associated with a VLAN, the type of firewall may impose restrictions on the number of devices that
reside on the VLAN.


## What kinds of devices are assigned to a VLAN?
{: faq}

Any device that has a network connection will be associated with a VLAN. Dedicated servers have both a public and private network connection, so you will see those devices associated with both public and private VLANs.


## How do I trunk my VLANs to my servers?
{: faq}

VLANs may only be trunked to bare metal servers through use of the API; no portal interface is available for this activity. 
For more information about managing VLANs as trunks, see the API documentation links below.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## When ordering a VLAN, what does it mean when I'm told there aren't any available VLANs?
{: faq}

See [A note about capacity](/docs/infrastructure/vlans?topic=vlans-getting-started#note-about-capacity).


## Why can't my devices communicate with one another on the same private VLAN?
{: faq}

If each server is on a different subnet, then by default, they will not be able to communicate via IP addresses. Technically, your servers can communicate using OSI Model Layer 2 methods because they are on the same VLAN (a Layer 2 construct). For internet protocol (IP) (also called Layer 3) communication to work, you can either add a route for the subnet you're attempting to communicate with on each server (the route is different on each server), or enable [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Note that [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) has additional implications, so review the feature in detail before deciding to enable it.

## What options do I have if I need devices on different private subnets within the same VLAN to communicate by default, but I don't want to enable VLAN Spanning?
{: faq}

If you cannot enable VLAN spanning but require some VLANs and subnets to route between each other, you can associate those VLANs with a firewall or gateway, and manage the routing and security to fit your needs. In addition, to route between Pods and data centers, all VLANs requiring connectivity need to be associated with the gateway device and an overlay, typically GRE tunnel(s), established between the gateway devices.

---

copyright:
  years: 1994, 2019
lastupdated: "2019-10-10"

keywords:

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# FAQs
{: #vlans-faqs}

Have a question about VLANs? Review frequently asked questions, which provide answers to provisioning concerns, application access, and other common inquiries.
{: shortdesc}

## Can I move an existing device to a new VLAN?
{: #move-existing-device-new-vlan}
{: faq}
{: support}

Existing compute devices, such as a virtual server instance (VSI) or a bare metal, cannot be moved to a new VLAN. A new VSI or bare metal must be provisioned in the new VLAN and deprovisioned accordingly. Single VLAN firewalls cannot be moved to a new VLAN either. Multi VLAN firewalls can be attached to the new VLAN and then detached from the previous VLAN. Refer to the specific offering documentation for capabilities and limitations.

## Is there a way to specify which VLAN I want to use for my device when I order it?
{: #specify-vlan-during-order}
{: faq}
{: support}

Yes, a specific VLAN can be selected during the ordering process. This option is available at the end of the device order form. A private VLAN is selected, followed by a public VLAN. Remember that a subnet selector is presented for each VLAN, and that this selection is **optional**. Select a subnet only if you have reason to do so because selecting a subnet that lacks available IP addresses negatively impacts the fulfillment of the device. See the [Subnet FAQ](/docs/subnets?topic=subnets-faq) for more details.

The selected VLAN must be located in the same data center as the device. We cannot assign a device to a VLAN that is in a different data center.
{: important}


## How many devices can be assigned to a single VLAN?
{: #number-of-devices-assigned-vlan}
{: faq}
{: support}

Currently, no limit exists for the number of devices that are associated with a single VLAN at any time. However, when a hardware firewall is associated with a VLAN, the type of firewall might impose restrictions on the number of devices that reside on the VLAN.


## What kinds of devices are assigned to a VLAN?
{: #kinds-of-devices-assigned-vlan}
{: faq}
{: support}

Any device that has a network connection is associated with a VLAN. Dedicated servers have both a public and private network connection, so you see those devices associated with both public and private VLANs.

## How do I trunk my VLANs to my servers?
{: #trunk-vlans-to-servers}
{: faq}
{: support}

VLANs can be trunked to bare metal servers only through use of the API; no portal interface is available for this activity.
For more information about managing VLANs as trunks, see the following API documentation links:

* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## As I order a VLAN, what does it mean when I'm told that no VLANs are available?
{: #no-vlans-available}
{: faq}
{: support}

If you are told that no VLANs are available, see [A note about capacity](/docs/vlans?topic=vlans-getting-started#note-about-capacity).

## Why can't my devices communicate with one another on the same private VLAN?
{: #devices-cant-communicate-on-private-vlan}
{: faq}
{: support}

If each server is on a different subnet, then by default, they are not able to communicate via IP addresses. Technically, your servers can communicate by using OSI Model Layer 2 methods because they are on the same VLAN (a Layer 2 construct). For Internet Protocol (IP) (also called Layer 3) communication to work, you can either of the following:

* Add a route for the subnet you're attempting to communicate with on each server (the route is different on each server)
* Enable [VLAN Spanning](/docs/vlans?topic=vlans-vlan-spanning)

Keep in mind that [VLAN Spanning](/docs/vlans?topic=vlans-vlan-spanning) has additional implications, so review the feature in detail before enabling it.

## What options do I have if I need devices on different private subnets within the same VLAN to communicate by default, but I don't want to enable VLAN Spanning?
{: #communicate-without-vlan-spanning}
{: faq}

If you cannot enable VLAN spanning but require some VLANs and subnets to route between each other, you can associate those VLANs with a firewall or gateway, and manage the routing and security to fit your needs. To route between Pods and data centers, all VLANs requiring connectivity must be associated with the gateway device and an overlay, typically GRE tunnels, established between the gateway devices.

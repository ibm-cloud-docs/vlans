---
copyright:
  years: 1994, 2017
lastupdated: "2018-11-09"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:faq: data-hd-content-type='faq'}

# FAQs


## Can I move an existing device to a new VLAN?
{: faq}

Existing devices can be moved to other VLANs, but only when the move is requested. Because VLANs are tied to a router and connections to each router are dependent upon the device's physical location, some VLAN moves may require a physical relocation, as well. This is always the case when the new VLAN is located in a different datacenter, but it also may apply when moving a device to a different VLAN within the same datacenter. Making this change interrupts network connectivity and requires changing the device's IP address when the connection is moved to the new VLAN. When moving a device to a new VLAN we ask that ample planning is allowed, because the machine will be offline for the duration of the move.


## Is there a way to specify which VLAN I want to use for my device when I order it?
{: faq}

Yes, a specific VLAN may be selected during the ordering process. When ordering a device, this option is available at the end of the order form. A private VLAN is selected, followed by a public VLAN. Also note that a subnet selector is presented for each VLAN; this selection is **optional**. Only select a subnet if you have reason to do so, as selecting a subnet which lacks available IP addresses will negatively impact the fulfillment of the device (See the [Subnet FAQ](../../infrastructure/subnets/faq.html) for more details).

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

See [A note about capacity](getting-started.html#a-note-about-capacity).


## Why can't my devices communicate with one another on the same private VLAN?
{: faq}

If each server is on a different subnet, then by default, they will not be able to communicate via IP addresses. Technically, your servers can communicate using OSI Model Layer 2 methods because they are on the same VLAN (a Layer 2 construct). For internet protocol (IP) (also called Layer 3) communication to work, you can either add a route for the subnet you're attempting to communicate with on each server (the route is different on each server), or enable [VLAN Spanning](vlan-spanning.html). Note that [VLAN Spanning](vlan-spanning.html) has additional implications, so review the feature in detail before deciding to enable it.


## What options do I have if I need devices on different private subnets within the same VLAN to communicate by default, but I don't want to enable VLAN Spanning?
{: faq}

We understand managing routes on servers is cumbersome considering {{site.data.keyword.cloud}} automatically assigns and removes Primary Subnets as needed. We also understand that [VLAN Spanning](vlan-spanning.html) is not always a possibility. If you have a large deployment that is hindered by this behavior, you may request an accommodating Primary Subnet on a
[Premium VLAN](about-vlans.html#premium-vlans) only. Charges will apply to this subnet, and may vary per request. It is at our discretion to grant or deny such requests on a case by case basis (not account by account, but each
request). Follow these instructions to request a specially sized Primary Subnet:

  1. Open the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.bluemix.net/){: new_window} and log into your account.
  2. In the menu, select **Infrastructure**.
  3. Order a Premium VLAN, if needed. See [Ordering Premium VLANs](getting-started.html).
  4. Open a ticket by navigating to **Support > Add Ticket** in the menu.
    - Subject: "Private Network Question" or "Public Network Question"
    - Title: "Large Primary Subnet Request"
    - Details: Specify the Premium VLAN you desire the subnet on using datacenter.router.vlan notation (for example, ams03.bcr01.1234). Then specify the desired subnet size in CIDR notation (for example, /25). Denote how many servers you plan on purchasing and over what time period. Additionally, explain how your usage would be hindered without the requested subnet. Be verbose in explaining how your situation would be hindered, because this input helps us evaluate improvements to our platform.

No other properties of the subnet will be considered, so there is no need for further specification.

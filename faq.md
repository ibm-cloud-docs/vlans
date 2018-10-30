---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-29"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# FAQs


## Can I move an existing device to a new VLAN?

Existing devices can be moved to other VLANs, but only when the move is
requested. Because VLANs are tied to a router and connections to each router are
dependent upon the device's physical location, some VLAN moves may require a
physical relocation, as well. This is always the case when the new VLAN is
located in a different datacenter, but it also may apply when moving a device to
a different VLAN within the same datacenter. Making this change interrupts
network connectivity and requires changing the device's IP address when the
connection is moved to the new VLAN. When moving a device to a new VLAN we ask
that ample planning is allowed, because the machine will be offline for the
duration of the move.


## Is there a way to specify which VLAN I want to use for my device when I order it?

Yes, a specific VLAN may be selected during the ordering process. When ordering
a device, this option is available at the end of the order form. A private VLAN
is selected, followed by a public VLAN. Also note that a subnet selector is
presented for each VLAN; this selection is **optional**. Only select a subnet if
you have reason to do so, as selecting a subnet which lacks available IP
addresses will negatively impact the fulfillment of the device (See the
[Subnet FAQ](https://console.bluemix.net/docs/infrastructure/subnets/faq.html)
for more details).

It is important to note that the selected VLAN must be located in the same
datacenter as the device. We cannot assign a device to a VLAN that is in a
different datacenter.


## How many devices may be assigned to a single VLAN?

There is currently no limit to the number of devices that are associated with a
single VLAN at any time; however, when a hardware firewall is associated with a
VLAN, the type of firewall may impose restrictions on the number of devices that
reside on the VLAN.


## What kinds of devices are assigned to a VLAN?

Any device that has a network connection will be associated with a VLAN.
Dedicated servers have both a public and private network connection, so you will
see those devices associated with both public and private VLANs.

## How do I trunk my VLANs to my servers?

VLANs may only be trunked to bare metal servers through use of the API; no portal interface is available for this activity. 
For more information for managing VLANs as trunks, see the API documentation links below.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks


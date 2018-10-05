---
copyright:
  years: 1994, 2017
lastupdated: "2018-10-05"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Getting Started with VLANs

Virtual Local Area Networks or VLANs are used by {{site.data.keyword.cloud}} to isolate broadcast traffic on the public and private networks. VLANs are assigned as needed to fulfill other offerings. For instance, if you place a compute order for a datacenter in which you don't yet have a presence, you'll automatically receive a VLAN. Additional compute orders for the same datacenter, which do not specify network requirements, usually are placed in the previously assigned VLAN. All VLANs that are assigned automatically are also removed automatically when your resources no longer require them. 

VLANs are specific to the routers used in IBM Cloud datacenters, and a datacenter contains multiple routers to handle the public and private networks. Thus, it is possible, that multiple VLANs can be assigned within a single datacenter. It also is possible to order additional VLANs to construct more complex network topologies; typically in conjunction with a [Virtual Router Appliance](https://console.bluemix.net/docs/infrastructure/virtual-router-appliance/getting-started.html).

Learn more about how VLANs operate in [About VLANs](about-vlans.html).


## Managing VLANs

Follow these steps to review the VLANs on your account:

  1. Open the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.bluemix.net/){: new_window} and log into your account.
  2. In the menu, select **Infrastructure**.
  3. In the Customer Portal navigation, select **Network > IP Management > VLANs**.

The VLANs listing displays information about your VLANs, and it provides access
to each VLAN, along with associated devices or subnets.


## Ordering VLANs

When you're ready to explore a more complex network topology, additional VLANs
can be used to isolate traffic between groups of devices. Unlike VLANs
automatically assigned to fulfill the needs of other products, a purchased VLAN
will remain on your account until canceled.

Order a VLAN by following these steps:

  1. Open a ticket at https://control.bluemix.net/ > Support > Add Ticket
    - check: Sales/Inquiry
    - check: Infrastructure
  2. Put that you would like to request an additional VLAN and attach the form:
     [vlan_request_form_fill_in.pdf](https://public.dhe.ibm.com/cloud/bluemix/network/vlans/vlan_request_form_fill_in.pdf)

### What Happens Next?

Support will contact you to complete the order. See [Getting Help](getting-help.html)
for more information on how to check the status of your ticket.

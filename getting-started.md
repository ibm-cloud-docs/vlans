---
copyright:
  years: 1994, 2017
lastupdated: "2018-09-05"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Getting Started with VLANs

Virtual Local Area Networks or VLANs are used by {{site.data.keyword.cloud}} to
isolate broadcast traffic on both the public and private networks. VLANs are
automatically assigned as needed to fulfill other offerings. For instance,
compute orders in a datacenter you don't yet have a presence in will
automatically receive a VLAN. Further compute orders for the same datacenter,
and which do not specify network requirements, will be placed in the previously
assigned VLAN (for the most part, other product factors can effect this). All
VLANs which are assigned automatically, are also removed automatically when
resources no longer require them. Don't be alarmed when a new VLAN is assigned
or an existing VLAN is removed.

VLANs are specific to the routers used in our datacenters, and a datacenter will
contain multiple routers for both the public and private networks. Thus, it is
possible, depending on the other products used, that multiple VLANs are assigned
within a single datacenter. It is also possible to order additional VLANs to
construct more complex network topologies; typically in conjunction with a
[Virtual Router Appliance](https://console.bluemix.net/docs/infrastructure
/virtual-router-appliance/getting-started.html).

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

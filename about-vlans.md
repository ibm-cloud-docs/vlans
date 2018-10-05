---
copyright:
  years: 1994, 2017
lastupdated: "2018-10-05"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# About VLANs

VLANs are central in directing traffic to your resources. You may never need to interact directly with any VLANs, because they are managed automatically: they are assigned as needed and removed when not.

A VLAN is network concept. It provides for creating broadcast domains at the [OSI Model ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://en.wikipedia.org/wiki/OSI_model) layer 2 level, the _data link layer_. VLANs provide one method of packet identification, and they allow multiple workloads to coexist on the same
physical equipment. For more information about VLANs, please refer to [this article ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://en.wikipedia.org/wiki/Virtual_LAN).


## VLAN Identification

VLANs exist on routers within IBM Cloud datacenters. Each VLAN is identified by a unique number, router, and datacenter location combination. For example, public `VLAN 829`, which is located on router `fcr02` within datacenter `SJC01` would be identified by `sjc01.fcr02.829`. Private VLAN 2234, located on router `bcr01` within datacenter `AMS01` would be identified by `ams01.bcr01.2234`.


## VLANs and Subnets

VLANs can contain one or more subnets. Like VLANs, some subnets are
automatically added and removed as devices require IP addresses. What subnets
can exist and how they operate are further detailed in [Subnets and
IPs](https://console.bluemix.net/docs/infrastructure/subnets/).


## Communication within a VLAN

All resources on a VLAN can communicate, but that does not mean they will by
default. It is important to remember that VLANs are a OSI Model Layer 2
construct and that subnet/IPs are a Layer 3 construct. Communication happens
differently at each layer. Resources in different VLANs, whether on the public
or private network cannot communicate with one another via layer 2 methods.

### Communication within a VLAN on the Public Network

There are no inherent restrictions to communication between resources on the
public network, whether on one or more VLANs within
{{site.data.keyword.cloud}}'s public network infrastructure or the internet.
Restrictions can be added by introducing a Firewall or Gateway Appliance.

### Communication within a VLAN on the Private Network

By default, only compute within the same subnet can communicate, even if multiple
subnets are in the same VLAN. However, it is possible to communicate with other
subnets on the same VLAN as long as the compute instances have route entries for
the additional subnets on that VLAN. Managing route entries on all compute nodes
which need to communicate across private subnets can be cumbersome. For these
situations in which default communication is required among all compute within
the same VLAN, see [VLAN Spanning](vlan-spanning.md).

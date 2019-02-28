---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: VLANs, different role, network concept

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}

# About VLANs
{:#about-vlans}

VLANs are central in directing traffic to your resources. You may never need to interact directly with any VLANs, because they are managed automatically: they are assigned as needed and removed when not.

A VLAN is a network concept. It allows you to create broadcast domains at the [OSI Model ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://en.wikipedia.org/wiki/OSI_model) layer 2 level, the _data link layer_. VLANs provide one method of packet identification, and they allow multiple workloads to coexist on the same
physical equipment. For more information about VLANs, refer to [this article ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://en.wikipedia.org/wiki/Virtual_LAN).

## Types of VLANs
{:#types-of-vlans}

There are two distinct types of VLANs which {{site.data.keyword.cloud}} refers to as **Automatic** and **Premium**. They each play a different role, and depending on your needs, understanding their differences is important.

### Automatic VLANs
{:#automatic-vlans}

Automatic VLANs are managed by {{site.data.keyword.cloud}} automatically; assigned and removed as needed in order to fulfill the needs of other products you order. You typically have one automatic VLAN per router. Automatic VLANs are associated to servers ordered without a specific VLAN selected. It is not possible to order or cancel automatic VLANs, because they only exist on your account when our systems determine they are required, and are removed when our systems determine they are no longer needed.

### Premium VLANs
{:#about-premium-vlans}

Premium VLANs are acquired by ordering a VLAN. See [Ordering Premium VLANs](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans) for instructions. Premium VLANs remain on your account until explicitly canceled. You may order as many premium VLANs as you like, subject to capacity limitations. In the event capacity is unavailable, seek VLANs in another pod or datacenter.

An important distinction of Premium VLANs is that they are not selected automatically to fulfill a server order. Premium VLANs must be explicitly selected during the server ordering process to have servers reside on them. See the [FAQ](/docs/infrastructure/vlans?topic=vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-) for instructions concerning VLAN selection.


## VLAN identification
{:#vlan-identification}

VLANs exist on routers within IBM Cloud datacenters. Each VLAN is identified by a unique number, router, and datacenter location combination. For example, public `VLAN 829`, which is located on router `fcr02` within datacenter `SJC01` is identified by `sjc01.fcr02.829`. Private VLAN 2234, located on router `bcr01` within datacenter `AMS01` is identified by `ams01.bcr01.2234`.


## VLANs and subnets
{:#vlans-subnets}

VLANs can contain one or more subnets. Like VLANs, some subnets are automatically added and removed as devices require IP addresses. What subnets can exist, and how they operate is further detailed in [Subnets and IPs](/docs/infrastructure/subnets?topic=subnets-getting-started-with-subnets-and-ips).


## Communication within a VLAN
{:#communication-within-vlans}

All resources on a VLAN can communicate, but that does not mean they will, by default. It is important to remember that VLANs are an OSI Model Layer 2 construct, and that subnet/IPs are a Layer 3 construct. Communication happens differently at each layer. Resources in different VLANs, whether on the public or private network, cannot communicate with one another via layer 2 methods.

### Communication within a VLAN on the public network
{:#communication-within-vlans-public}

There are no inherent restrictions to communication between resources on the public network, whether on one or more VLANs within {{site.data.keyword.cloud}}'s public network infrastructure or the internet. Restrictions can be added by introducing a Firewall or Gateway Appliance.

### Communication within a VLAN on the private network
{:#communication-within-vlans-private}

By default, only compute within the same subnet can communicate, even if multiple subnets are in the same VLAN. However, it is possible to communicate with other subnets on the same VLAN as long as the compute instances have route entries for
the additional subnets on that VLAN. Managing route entries on all compute nodes which need to communicate across private subnets can be cumbersome. For the situations in which default communication is required among all compute within the same VLAN, see [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Note that VLAN Spanning has broad implications and should be reviewed carefully before enabling.

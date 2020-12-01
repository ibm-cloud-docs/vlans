---

copyright:
  years: 1994, 2020
lastupdated: "2020-08-14"

keywords:  

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

# About VLANs
{:#about-vlans}

VLANs are central in directing traffic to your resources. You might never need to interact directly with any VLANs because they are managed automatically: they are assigned as needed and removed when not.

A VLAN is a network concept. VLANs allow you to create broadcast domains at the [OSI Model](https://en.wikipedia.org/wiki/OSI_model){:external} layer 2 level, the _data link layer_. VLANs provide one method of packet identification, and they allow multiple workloads to coexist on the same physical equipment. For more information about VLANs, refer to [this article](https://en.wikipedia.org/wiki/Virtual_LAN){:external}.
{:shortdesc}

## Types of VLANs
{:#types-of-vlans}

{{site.data.keyword.cloud}} refers to the two distinct types of VLANs as **Automatic** and **Premium**. They each play a different role, and depending on your needs, understanding their differences is important.

### Automatic VLANs
{:#automatic-vlans}

Automatic VLANs are managed by {{site.data.keyword.cloud}} automatically. They're assigned and removed as needed to fulfill the needs of other products you order. You typically have one automatic VLAN per router. Automatic VLANs are associated to servers ordered without a specific VLAN selected. It's not possible to order or cancel automatic VLANs because they exist on your account only when our systems determine they are required. They're removed when our systems determine they are no longer needed.

### Premium VLANs
{:#about-premium-vlans}

Premium VLANs are acquired by ordering a VLAN. See [Ordering Premium VLANs](/docs/vlans?topic=vlans-ordering-premium-vlans) for instructions. Premium VLANs remain on your account until explicitly canceled. You can order as many premium VLANs as you like, subject to capacity limitations. If capacity is unavailable, seek VLANs in another pod or data center.

An important distinction of Premium VLANs is that they're not selected automatically to fulfill a server order. Premium VLANs must be explicitly selected while you are ordering servers, to have servers reside on them. See the [FAQ](/docs/vlans?topic=vlans-vlans-faqs#specify-vlan-during-order) for instructions on VLAN selection.


## VLAN identification
{:#vlan-identification}

VLANs exist on routers within IBM Cloud data centers. Each VLAN is identified by a unique number, router, and data center location combination. For example, public `VLAN 829`, which is on router `fcr02` within data center `SJC01` is identified by `sjc01.fcr02.829`. Private `VLAN 2234`, on router `bcr01` within data center `AMS01` is identified by `ams01.bcr01.2234`.


## VLANs and subnets
{:#vlans-subnets}

VLANs can contain one or more subnets. Like VLANs, some subnets are automatically added and removed as devices require IP addresses. What subnets can exist, and how they operate is further detailed in [Subnets and IPs](/docs/subnets?topic=subnets-getting-started).


## Communication within a VLAN
{:#communication-within-vlans}

All resources on a VLAN can communicate, but that does not mean they will, by default. Remember that VLANs are an OSI Model Layer 2 construct, and that subnet/IPs are a Layer 3 construct. Communication happens differently at each layer. Resources in different VLANs, whether on the public or private network, cannot communicate with one another via layer 2 methods.

### Communication within a VLAN on the public network
{:#communication-within-vlans-public}

Communication between resources on the public network is not inherently restricted, whether on one or more VLANs within {{site.data.keyword.cloud}}'s public network infrastructure or the internet. Restrictions can be added by introducing a Firewall or Gateway Appliance.

### Communication within a VLAN on the private network
{:#communication-within-vlans-private}

By default, only compute within the same subnet can communicate, even if multiple subnets are in the same VLAN. However, it is possible to communicate with other subnets on the same VLAN, provided that the compute instances have route entries for the additional subnets on that VLAN. Managing route entries on all compute nodes that need to communicate across private subnets can be cumbersome. See [VLAN Spanning](/docs/vlans?topic=vlans-vlan-spanning) for how to handle situations where default communication is required among all compute within the same VLAN. Review VLAN Spanning carefully before enabling, because it has broad implications.

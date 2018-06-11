---
copyright:
  years: 1994, 2017
lastupdated: "2018-06-06"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Getting Started with VLANs

A VLAN is a Virtual Local Area Network, which can be created to permit customers to separate parts of a larger network into smaller subnets. A VLAN works as a container within which a single customer's connections and IP addresses can remain separate from any other customer. VLANs allow for better security and for isolation of certain issues. On our {{site.data.keyword.BluSoftlayer_notm}} network, VLANs provide the ability to partition your devices and subnets.

You may manage your VLANs from the VLANs screen:

1. Open the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.bluemix.net/){: new_window} and log into your account.
2. In the menu, select **Infrastructure**.
3. In the Customer Portal navigation, select **Network > IP Management > VLANs**.

The VLANs screen displays information about your VLANs, and it provides access to each VLAN, along with associated devices or subnets. As an added service, customers may enable VLAN Spanning, which connects all private network VLANs on an account, thereby allowing devices on separate VLANs to communicate with each other.

## VLAN Identification

VLANs exist on routers within our datacenters. Each VLAN is identified by a unique number, router, and datacenter location. For example, `VLAN 829`, which is located on router `fcr02` within datacenter `SJC01` is identified by our systems as `829 fcr02.sjc01`.

## VLAN Spanning

VLAN spanning is an account setting that enables traffic to travel between private VLANs that belong to a single account. Due to the nature of the private network, very little traffic is allowed into an account's private VLANs. In general, VLANs protect devices from network traffic on other customer accounts. Private VLANs take this protection a step further by restricting traffic on the VLAN to occur only between devices on that VLAN; therefore, by default, devices that are located on two different private VLANs may not send traffic to one another. By [enabling VLAN spanning](vlan-spanning.html), this restriction is lifted so that devices on one account's different private VLANs may communicate.

### When should I enable VLAN spanning for my account?

VLAN spanning should be enabled whenever the business need arises. For example, if servers that reside on more than one private subnet need to communicate, VLAN spanning should be enabled. Communication between VLANs is not specific to the physical location of the VLAN; for example, private VLANs in the same datacenter are still entirely segregated from one another. When devices are located in two or more VLANs, each with their own subnet, VLAN spanning must be enabled for the devices to communicate.

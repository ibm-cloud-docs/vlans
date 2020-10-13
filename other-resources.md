---

copyright:
  years: 1994, 2019
lastupdated: "2019-07-08"

keywords: VLAN Spanning resources

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:term: .term}
{:tip: .tip}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:table: .aria-labeledby="caption"}
{:generic: data-hd-programlang="generic"}
{:download: .download}
{:DomainName: data-hd-keyref="DomainName"}

# Resources for VLAN spanning
{:#other-resources-vlan-spanning}

You must enable VLAN spanning for your {{site.data.keyword.cloud_notm}} infrastructure account so your worker nodes can communicate with each other on the private network if you have multiple VLANs for a cluster, multiple subnets on the same VLAN, or a multizone cluster.
{:shortdesc}

If you do not have the correct access to perform this action, you can ask the account owner to enable it. If you're unsure about whether VLAN spanning is enabled, you can run `ibmcloud ks vlan-spanning-get` to see your account status.

You often need to enable VLAN spanning when you work with [{{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-getting-started). If you are using {{site.data.keyword.BluDirectLink}}, you must use a [Virtual Router Function (VRF)](/docs/direct-link?topic=direct-link-configure-ibm-cloud-direct-link#more-about-using-vrf) instead. To enable VRF, contact your {{site.data.keyword.cloud_notm}} infrastructure account representative.

For help with specific VLANs tasks, refer to the following resources.

* [Premium VLANs](https://www.ibm.com/cloud/blog/introducing-premium-vlans-are-you-compute-first-or-network-first)
* [For Kubernetes service, configure edge nodes with multiple VLANs](/docs/containers?topic=containers-loadbalancer#edge_nodes_multiple_vlans)
* [IBM Cloud CLI commands for VLANs](/docs/cli?topic=cli-manage-classic-vlans)
* [Managing VLANs with a Gateway Appliance](/docs/vsrx?topic=gateway-appliance-managing-vlans-and-gateway-appliances)
* [Enabling routing between primary subnets on the same VLAN](/docs/containers?topic=containers-subnets#basics_segmentation)

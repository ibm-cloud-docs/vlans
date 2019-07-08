---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-07-08"

keywords: IBM Cloud infrastructure, private network, VLAN Spanning, VLANs

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}

# Other resources for VLAN spanning
{:#other-resources-vlan-spanning}

If you have multiple VLANs for a cluster, multiple subnets on the same VLAN, or a multizone cluster, you must enable VLAN spanning for your {{site.data.keyword.cloud_notm}} infrastructure account so your worker nodes can communicate with each other on the private network. If you do not have the correct access to perform this action, you can request that the account owner enable it. If you're unsure about whether VLAN spanning is enabled, you can run `ibmcloud ks vlan-spanning-get` to see your account status.

When working with [{{site.data.keyword.containerlong_notm}}](/docs/containers?topic=containers-getting-started), you frequently need to enable VLAN spanning. If you are using {{site.data.keyword.BluDirectLink}}, you must use a [Virtual Router Function (VRF)](/docs/infrastructure/direct-link?topic=direct-link-configure-ibm-cloud-direct-link#more-about-using-vrf) instead. To enable VRF, contact your {{site.data.keyword.cloud_notm}} infrastructure account representative.

For help with specific tasks involving VLANs, refer to the following resources. 

* [Premium VLANs](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [Tutorial on setting up classic VLAN spanning using VRAs](/docs/tutorials?topic=solution-tutorials-vlan-spanning#vlan-spanning)
* [For Kubernetes service, configuring edge nodes with multiple VLANs](/docs/containers?topic=containers-loadbalancer#edge_nodes_multiple_vlans)
* [IBM Cloud CLI commands for VLANs](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Route multiple VLANs over the same network interface using Juniper vSRX](/docs/infrastructure/vsrx?topic=vsrx-managing-ibm-vlans#route-multiple-vlans-over-the-same-network-interface)
* [Configuring subnets for Kubernetes clusters](/docs/containers?topic=containers-subnets#vlan-spanning)
* [Overview of IBM Cloud Networking, VLAN spanning for VMware solutions](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)

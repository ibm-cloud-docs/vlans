---
copyright:
  years: 1994, 2017-2019
lastupdated: "2019-01-02"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Other resources for VLAN spanning

When working with [{{site.data.keyword.containerlong_notm}}](/docs/containers/container_index.html), you frequently need to enable VLAN spanning. If you have multiple VLANs for a cluster, multiple subnets on the same VLAN, or a multizone cluster, you must enable VLAN spanning for your {{site.data.keyword.Bluemix_notm}} infrastructure account so your worker nodes can communicate with each other on the private network. If you do not have the correct access to perform this action, you can request that the account owner enable it. If you're unsure about whether VLAN spanning is enabled, you can run `ibmcloud ks vlan-spanning-get` to see your account status.

If you are using {{site.data.keyword.BluDirectLink}}, you must use a [Virtual Router Function (VRF)](/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf) instead. To enable VRF, contact your {{site.data.keyword.Bluemix_notm}} infrastructure account representative.

For help with specific tasks involving VLANs, refer to the following resources. 

* [Premium VLANs](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [Tutorial on setting up classic VLAN spanning using VRAs](../tutorials/vlan-spanning.html#vlan-spanning)
* [For Kubernetes service, configuring edge nodes with multiple VLANs](../containers/cs_loadbalancer.html#edge_nodes_multiple_vlans)
* [IBM Cloud CLI commands for VLANs](../cli/reference/ibmcloud/cli_vlan.html)
* [Route multiple VLANs over the same network interface using Juniper vSRX](../infrastructure/vsrx/manage-vlans.html#route-multiple-vlans-over-the-same-network-interface)
* [Configuring subnets for Kubernetes clusters](../containers/cs_subnets.html#vlans)
* [Overview of IBM Cloud Networking, VLAN spanning for VMware solutions](../services/vmwaresolutions/archiref/vcsnsxt/vcsnsxt-overview-ic4vnetwork.html#vlan-spanning)

---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: IBM Cloud Kubernetes Service, IBM Cloud infrastructure account, private network

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}

# VLAN 生成的其他资源
{:#other-resources-vlan-spanning}

在使用 [{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html) 时，经常需要启用 VLAN 生成。如果您具有针对一个集群的多个 VLAN、相同 VLAN 上的多个子网或者多区域集群，那么必须针对 {{site.data.keyword.Bluemix_notm}} 基础架构帐户启用 VLAN 生成，从而使专用网络上的工作程序节点可相互通信。如果您没有正确的访问权来执行此操作，那么可以请求帐户所有者启用此功能。如果您不确定是否已启用 VLAN 生成，可以运行 `ibmcloud ks vlan-spanning-get` 以查看帐户状态。

如果使用 {{site.data.keyword.BluDirectLink}}，那么必须改为使用[虚拟路由器功能 (VRF)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf)。要启用 VRF，请联系 {{site.data.keyword.Bluemix_notm}} 基础架构客户代表。

有关涉及 VLAN 的特定任务的帮助，请参阅以下资源。 

* [高级 VLAN](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [有关使用 VRA 设置 VLAN 生成的教程](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [对于 Kubernetes 服务，配置具有多个 VLAN 的边缘节点](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [针对 VLAN 的 IBM Cloud CLI 命令](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [使用 Juniper vSRX 在相同网络接口上路由多个 VLAN](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [针对 Kubernetes 集群配置子网](/docs/containers?topic=containers-subnets#vlan-spanning)
* [针对 VMware 解决方案的 IBM Cloud 联网和 VLAN 生成的概述](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


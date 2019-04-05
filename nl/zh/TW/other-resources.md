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

# VLAN Spanning 的其他資源
{:#other-resources-vlan-spanning}

使用 [{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html) 時，您經常需要啟用 VLAN Spanning。如果您的叢集有多個 VLAN、相同 VLAN 上有多個子網路，或是有多區域叢集，您必須為 {{site.data.keyword.Bluemix_notm}} 基礎架構帳戶啟用 VLAN Spanning，讓專用網路上的工作者節點能彼此通訊。如果您沒有正確的存取權可以執行此動作，您可以要求帳戶擁有者啟用它。如果您不確定是否已啟用 VLAN Spanning，可以執行 `ibmcloud ks vlan-spanning-get` 來查看帳戶狀態。

如果您使用 {{site.data.keyword.BluDirectLink}}，則必須改為使用[虛擬路由器功能 (VRF)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf)。若要啟用 VRF，請與您的 {{site.data.keyword.Bluemix_notm}} 基礎架構帳戶代表聯絡。

如需關於 VLAN 之特定作業的協助，請參閱下列資源。 

* [Premium VLANs](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [使用 VRA 設定標準 VLAN Spanning 的指導教學](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [針對 Kubernetes 服務，配置具有多個 VLAN 的邊緣節點](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [VLAN 的 IBM Cloud CLI 指令](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [使用 Juniper vSRX 在相同網路介面上遞送多個 VLAN](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [配置 Kubernetes 叢集的子網路](/docs/containers?topic=containers-subnets#vlan-spanning)
* [IBM Cloud 網路概觀，VMware 解決方案的 VLAN Spanning](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


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

# VLAN スパンニングのための他のリソース
{:#other-resources-vlan-spanning}

[{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html) を使用する場合には、VLAN スパンニングを有効にしなければならないことがよくあります。1 つのクラスターに複数の VLAN がある場合、同じ VLAN 上に複数のサブネットがある場合、または複数ゾーン・クラスターがある場合は、{{site.data.keyword.Bluemix_notm}} インフラストラクチャー・アカウントで VLAN スパンニングを有効にして、プライベート・ネットワーク上のワーカー・ノードが相互通信できるようにする必要があります。この操作を実行する適切なアクセス権がない場合は、アカウント所有者に有効化を依頼してください。VLAN が有効になっているかどうかがわからない場合は、`ibmcloud ks vlan-spanning-get` を実行してアカウントの状況を確認できます。

{{site.data.keyword.BluDirectLink}} を使用している場合には、[Virtual Router Function (VRF)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf) を代わりに使用する必要があります。VRF を有効にするには、{{site.data.keyword.Bluemix_notm}} インフラストラクチャー・アカウント担当者にお問い合わせください。

VLAN に関連する特定のタスクに役立つ以下のリソースを参照してください。 

* [プレミアム VLAN](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [VRA を使用してクラシック VLAN スパンニングをセットアップするためのチュートリアル](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [Kubernetes サービス用に、複数の VLAN を使用してエッジ・ノードを構成する方法](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [VLAN 用 IBM Cloud CLI コマンド](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Juniper vSRX を使用して同じネットワーク・インターフェース上で複数の VLAN を経路指定する](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [Kubernetes クラスター用のサブネットの構成](/docs/containers?topic=containers-subnets#vlan-spanning)
* [IBM Cloud ネットワーキング、VMware ソリューション用 VLAN スパンニングの概要](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


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

# 기타 VLAN Spanning 리소스
{:#other-resources-vlan-spanning}

[{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html)에 대해 작업할 때 종종 VLAN Spanning을 사용하도록 설정해야 합니다. 클러스터의 VLAN이 여러 개이거나 동일한 VLAN에 여러 서브넷이 있거나 다중 구역 클러스터가 있으면, 작업자 노드가 사설 네트워크에서 서로 통신할 수 있도록 {{site.data.keyword.Bluemix_notm}} 인프라 계정에 VLAN Spanning을 사용하도록 설정해야 합니다. 이 조치를 수행하는 데 올바른 액세스 권한이 없으면 계정 소유자에게 이를 사용으로 설정하도록 요청할 수 있습니다. VLAN Spanning이 사용으로 설정되었는지가 확실하지 않으면 `ibmcloud ks vlan-spanning-get`을 실행하여 계정 상태를 확인할 수 있습니다.

{{site.data.keyword.BluDirectLink}}를 사용하는 경우 [VRF(Virtual Router Function)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf)를 대신 사용해야 합니다. VRF를 사용하려면 {{site.data.keyword.Bluemix_notm}} 인프라 계정 담당자에게 문의하십시오.

VLAN과 관련된 특정 태스크에 관한 도움말은 다음 리소스를 참조하십시오. 

* [프리미엄 VLAN](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [VRA를 사용하여 클래식 VLAN Spanning 설정 튜토리얼](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [Kubernetes 서비스의 경우 여러 VLAN이 있는 에지 노드 구성](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [VLAN용 IBM Cloud CLI 명령](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Juniper vSRX를 사용하여 동일한 네트워크 인터페이스에 여러 VLAN 라우트](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [Kubernetes 클러스터의 서브넷 구성](/docs/containers?topic=containers-subnets#vlan-spanning)
* [IBM Cloud Networking, VLAN spanning for VMware 솔루션 개요](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


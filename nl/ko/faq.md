---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: new VLAN, subnet selector, VLAN moves

subcollection: vlans

---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}
{:faq: data-hd-content-type='faq'}

# FAQ
{:#vlans-faqs}


## 기존 디바이스를 새 VLAN으로 이동할 수 있습니까?
{: faq}

기존 디바이스가 다른 VLAN으로 이동될 수 있지만, 이동이 요청될 때만 가능합니다. VLAN은 라우터에 연결되고 각 라우터에 대한 연결은 디바이스의 실제 위치에 종속되기 때문에 일부 VLAN 이동은 물리적 재배치가 필요할 수도 있습니다. 이것은 항상 새 VLAN이 다른 데이터 센터에 위치하는 경우이지만, 디바이스를 동일한 데이터 센터 내의 다른 VLAN으로 이동할 때도 적용될 수 있습니다. 이렇게 변경하면 네트워크 연결성을 인터럽트하며 연결이 새 VLAN으로 이동될 때 디바이스의 IP 주소를 변경해야 합니다. 디바이스를 새 VLAN으로 이동할 때, 머신이 이동 기간 동안 오프라인이 되기 때문에 충분한 계획을 세우는 것이 좋습니다.


## 디바이스를 주문할 때 내 디바이스에 대해 사용할 VLAN을 지정하는 방법이 있습니까?
{: faq}

예. 주문 프로세스 중에 특정 VLAN을 선택할 수 있습니다. 디바이스 주문 시, 이 옵션은 주문 양식의 끝 부분에 있습니다. 사설 VLAN이 선택되고, 그 후에 공용 VLAN이 선택됩니다. VLAN마다 서브넷 선택기가 제공된다는 점도 참고하십시오. 이 선택사항은 **선택적**입니다. 사용 가능한 IP 주소가 없는 서브넷을 선택하면 디바이스 이행에 부정적인 영향을 미칠 수 있으므로 서브넷을 선택해야 할 이유가 있는 경우에만 선택하십시오(자세한 정보는 [서브넷 FAQ](/docs/infrastructure/subnets?topic=subnets-subnets-faq) 참고).

선택한 VLAN이 디바이스와 동일한 데이터 센터에 위치해야 함을 유의하십시오. 디바이스를 다른 데이터 센터에 있는 VLAN에 지정할 수 없습니다.


## 단일 VLAN에 얼마나 많은 디바이스를 지정할 수 있습니까?
{: faq}

현재로서는 언제든 단일 VLAN과 연관되는 디바이스 수에 대한 제한이 없습니다. 그러나, 하드웨어 방화벽이 VLAN과 연관될 때는 방화벽 유형이 VLAN에 상주하는 디바이스 수에 대한 제한을
부과할 수 있습니다.


## 어떤 종류의 디바이스가 VLAN에 지정됩니까?
{: faq}

네트워크 연결을 갖는 모든 디바이스가 VLAN과 연관됩니다. 전용 서버는 공용 및 사설 네트워크 연결을 둘 다 갖고 있으므로, 공용 및 사설 VLAN과 연관된 디바이스를 볼 수 있습니다.

## 내 VLAN을 내 서버에 트렁킹하는 방법은 무엇입니까?
{: faq}

VLAN은 API를 통해서만 Bare Metal Server에 트렁킹될 수 있습니다. 이 활동에 포털 인터페이스를 사용할 수 없습니다.
VLAN을 트렁크로 관리하는 데 관한 자세한 정보는 아래 API 문서 링크를 참조하십시오.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## VLAN을 주문할 때 사용 가능한 VLAN이 없다고 표시되는 의미는 무엇입니까?
{: faq}

[용량에 관한 참고](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity)를 참조하십시오.


## 동일한 사설 VLAN에서 디바이스가 서로 통신할 수 없는 이유는 무엇입니까?
{: faq}

각 서버가 다른 서브넷에 있으면 기본적으로 IP 주소를 통해 통신할 수 없습니다. 기술적으로 서버는 동일한 VLAN(계층 2 구조)에 있으므로 OSI 모델 계층 2 방법을 사용하여 통신할 수 있습니다. 계층 3이라고도 하는 IP(Internet Protocol) 통신이 작동하려면 각 서버에서 통신할 서브넷의 라우트를 추가하거나(라우트는 서버마다 다름) [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)을 사용하도록 설정할 수 있습니다. [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)을 사용하면 추가 영향이 있으므로 이를 사용하도록 설정하기 전에 기능을 자세히 검토하십시오.


## 동일한 VLAN의 서로 다른 사설 서브넷에 있는 디바이스가 기본적으로 통신해야 하지만 VLAN Spanning을 사용하지 않으려는 경우 어떤 옵션을 사용할 수 있습니까?
{: faq}

{{site.data.keyword.cloud}}에서 필요한 대로 기본 서브넷을 자동으로 지정하고 제거한다는 점을 고려하면 서버에서 라우트를 관리하기가 번거롭다는 점을 알고 있습니다. [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)을 사용할 수 없는 경우도 있다는 점도 이해하고 있습니다. 이 동작으로 인해 대규모 배치에 방해가 되는 경우 [프리미엄 VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans)에서만
기본 서브넷을 수용하도록 요청할 수 있습니다. 비용 청구는 이 서브넷에 적용되며 요청마다 달라질 수 있습니다. 경우에 따라(계정별이 아니라 각 요청별) 당사의 임의 재량에 따라 이러한 요청을 허가하거나 거부할 수 있습니다. 다음 지시사항을 따라 특별하게 규모가 지정된 기본 서브넷을 요청하십시오.

  1. [IBM Cloud 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/){: new_window}을 열고 계정에 로그인하십시오.
  1. 메뉴에서 **클래식 인프라**를 선택하십시오. 
  1. 클래식 인프라 탐색 메뉴에서 **네트워크 > IP 관리> VLAN**을 선택하십시오.
  1. 필요하면 프리미엄 VLAN을 주문하십시오. [프리미엄 VLAN 주문](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans)을 참조하십시오.
  1. 메뉴에서 **지원 > 티켓 추가**로 이동하여 티켓을 여십시오.
    - 주제: "사설 네트워크 질문" 또는 "공용 네트워크 질문"
    - 제목: "대규모 기본 서브넷 요청"
    - 세부사항: datacenter.router.vlan 표기법(예: ams03.bcr01.1234)을 사용하여 서브넷을 둘 프리미엄 VLAN을 지정하십시오. 그런 다음 CIDR 표기법으로 원하는 서브넷 크기를 지정하십시오(예: /25). 구매할 계획인 서버 수와 해당 기간을 표시하십시오. 또한 요청된 서브넷이 없으면 사용에 어떤 지장을 주는지 설명하십시오. 당사에서 플랫폼 개선사항을 평가하는 데 도움이 되므로 상황에 어떤 지장을 주는지 상세하게 설명하십시오. 서브넷의 다른 특성은 고려하지 않으므로 추가 사양은 명시할 필요가 없습니다.

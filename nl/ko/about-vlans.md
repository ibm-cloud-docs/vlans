---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: VLANs, different role, network concept

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}

# VLAN 정보
{:#about-vlans}

VLAN은 리소스로 트래픽을 전달하는 데 중심이 됩니다. VLAN은 자동으로 관리되어 필요할 때 지정되고 필요하지 않을 때 제거되므로 VLAN과 직접 상호작용하지 않아도 됩니다.

VLAN은 네트워크 개념입니다. [OSI 모델 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://en.wikipedia.org/wiki/OSI_model) 계층 2 레벨, _데이터 링크 계층_에서 브로드캐스트 도메인을 작성할 수 있습니다. VLAN에서는 한 가지 패킷 식별 방법을 제공하며 동일한 실제 장비에 여러 워크로드가
공존할 수 있습니다. VLAN에 관한 자세한 정보는 [이 기사 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://en.wikipedia.org/wiki/Virtual_LAN)를 참조하십시오.

## VLAN 유형
{:#types-of-vlans}

{{site.data.keyword.cloud}}에서 **자동** 및 **프리미엄**으로 참조하는 두 가지 유형의 VLAN이 있습니다. 각 유형은 사용자의 요구사항에 따라 서로 다른 역할을 수행하므로, 차이점을 이해하는 것이 중요합니다.

### 자동 VLAN
{:#automatic-vlans}

자동 VLAN은 {{site.data.keyword.cloud}}에서 자동으로 관리합니다. 즉, 사용자가 주문하는 기타 제품의 요구사항을 이행하기 위해 필요한 대로 지정되고 제거됩니다. 일반적으로 라우터당 자동 VLAN이 하나씩 있습니다. 자동 VLAN은 특정 VLAN을 선택하지 않고 주문한 서버와 연관됩니다. 자동 VLAN은 시스템에서 필요하다고 판별하는 경우에만 계정에 존재하고 더 이상 필요하지 않다고 판별하면 제거되므로, 자동 VLAN을 주문하거나 취소할 수 없습니다.

### 프리미엄 VLAN
{:#about-premium-vlans}

프리미엄 VLAN은 VLAN을 주문하여 얻습니다. 지시사항은 [프리미엄 VLAN 주문](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans)을 참조하십시오. 프리미엄 VLAN은 명시적으로 취소할 때까지 계정에 남아 있습니다. 원하는 만큼 많은 수의 프리미엄 VLAN을 주문할 수 있지만, 용량 제한사항이 적용될 수 있습니다. 용량을 사용할 수 없는 경우 다른 팟(Pod)이나 데이터 센터에서 VLAN을 찾으십시오.

프리미엄 VLAN은 서버 주문을 이행하기 위해 자동으로 선택되지 않는다는 중요한 차이점이 있습니다. 프리미엄 VLAN에 서버가 상주하게 하려면 서버 주문 프로세스 중에 명시적으로 프리미엄 VLAN을 선택해야 합니다. VLAN 선택에 관한 지시사항은 [FAQ](/docs/infrastructure/vlans?topic=vlans-vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-)를 참조하십시오.


## VLAN 식별
{:#vlan-identification}

VLAN은 IBM Cloud 데이터 센터의 라우터에 있습니다. 각 VLAN은 고유한 번호, 라우터 및 데이터 센터 위치 조합으로 식별됩니다. 예를 들어 `SJC01` 데이터 센터의 `fcr02` 라우터에 있는 공용 `VLAN 829`는 `sjc01.fcr02.829`로 식별됩니다. `AMS01` 데이터 센터의 `bcr01` 라우터에 있는 사설 VLAN 2234는 `ams01.bcr01.2234`로 식별됩니다.


## VLAN 및 서브넷
{:#vlans-subnets}

VLAN에는 하나 이상의 서브넷이 포함될 수 있습니다. 디바이스에 IP 주소가 필요하므로 일부 서브넷은 VLAN과 마찬가지로 자동으로 추가되고 제거됩니다. 존재 가능한 서브넷 및 작동 방식은 [서브넷 및 IP](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips)에 자세히 설명되어 있습니다.


## VLAN 내의 통신
{:#communication-within-vlans}

VLAN의 모든 리소스가 통신할 수 있지만, 기본적으로 통신한다는 의미는 아닙니다. VLAN은 OSI 모델 계층 2 구조이고 서브넷/IP는 계층 3 구조라는 점을 기억해야 합니다. 통신은 각 계층에서 서로 다르게 수행됩니다. 현재 위치한 네트워크(공용 또는 사설)에 상관없이 서로 다른 VLAN에 있는 리소스는 계층 2 방법을 통해 서로 통신할 수 없습니다.

### 공용 네트워크의 VLAN에서 통신
{:#communication-within-vlans-public}

{{site.data.keyword.cloud}}의 공용 네트워크 인프라에 있는 하나 이상의 VLAN에 있는지 아니면 인터넷에 있는지에 상관없이 공용 네트워크의 리소스 간 통신에는 내재하는 제한사항이 없습니다. 방화벽이나 게이트웨이 어플라이언스를 도입하여 제한사항을 추가할 수 있습니다.

### 사설 네트워크의 VLAN에서 통신
{:#communication-within-vlans-private}

동일한 VLAN에 여러 서브넷이 있는 경우에도 기본적으로 동일한 서브넷의 컴퓨팅만 통신할 수 있습니다. 그러나 컴퓨팅 인스턴스에 동일한 VLAN의 추가 서브넷을 위한 라우트 항목이 있는 경우 해당 VLAN의 다른 서브넷과 통신할 수 있습니다. 사설 서브넷 간에 통신해야 하는 모든 컴퓨팅 노드에서 라우트 항목을 관리하기는 번거로울 수 있습니다. 동일한 VLAN의 모든 컴퓨팅 간에 기본 통신이 필요한 경우 [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)을 참조하십시오. VLAN Spanning은 광범위한 영향을 미치므로 이를 사용하도록 설정하기 전에 신중하게 검토해야 합니다.

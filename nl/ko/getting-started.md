---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: compute order, Additional compute orders, Premium VLANs

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:download: .download}
{:important: .important}
{:note: .note}
{:DomainName: data-hd-keyref="DomainName"}

# VLAN 시작하기
{:#getting-started-with-vlans}

가상 근거리 통신망(VLAN)은 {{site.data.keyword.cloud}}에서 공용 및 사설 네트워크에서 브로드캐스트 트래픽을 격리하는 데 사용합니다. VLAN은 다른 오퍼링을 이행하기 위해 필요한 대로 지정됩니다. 예를 들어 아직 사용자가 존재하지 않는 데이터 센터의 컴퓨팅 주문을 하는 경우 자동으로 VLAN을 받습니다. 네트워크 요구사항을 지정하지 않는 동일한 데이터 센터의 추가 컴퓨팅 주문은 일반적으로 이전에 지정된 VLAN에서 수행됩니다. 리소스에 더 이상 필요하지 않게 되면 자동으로 지정된 모든 VLAN도 자동으로 제거됩니다.

VLAN은 IBM Cloud 데이터 센터에서 사용하는 라우터별로 다르며 데이터 센터에는 공용 네트워크와 사설 네트워크 모두의 라우터가 여러 개 포함되어 있습니다. 따라서 단일 데이터 센터에 여러 VLAN을 지정할 수 있습니다. 일반적으로 [가상 라우터 어플라이언스](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance)와 결합하여 더 복잡한 네트워크 토폴로지를 생성하기 위해 추가 VLAN도 주문할 수 있습니다.

구매한 VLAN은 **프리미엄 VLAN**이라고 하며 VLAN은 {{site.data.keyword.cloud}}에서 **자동 VLAN**으로 자동 관리합니다. VLAN이 [VLAN 정보](/docs/infrastructure/vlans?topic=vlans-about-vlans)에서 작동하는 방식에 관해 자세히 알아보십시오.


## VLAN 관리
{:#managing-vlans}

다음 단계를 따라 계정의 VLAN을 검토하십시오.

  1. [IBM Cloud 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/){: new_window}을 열고 계정에 로그인하십시오.
  2. 메뉴에서 **인프라**를 선택하십시오.
  3. 고객 포털 탐색에서 **네트워크 > IP 관리> VLAN**을 선택하십시오.

VLAN 목록은 VLAN에 관한 정보를 표시하며, 연관된 디바이스 또는 서브넷과 함께 각 VLAN에 액세스할 수 있습니다.

### 팟(Pod)과 데이터 센터 선택 이해
{:#pod-vs-datacenter-selection}

여러 다른 요구사항과 제한조건에 맞게 VLAN 주문 위치 옵션이 제공됩니다. 이 섹션에서는 각 옵션을 선택하는 이유를 요약합니다.

**팟(Pod)별 주문** 옵션을 사용하면 VLAN이 필요한 정확한 팟(따라서 라우터)을 지정할 수 있습니다. 해당 팟(Pod)에 VLAN이 있어야 하는 구체적인 이유가 있으면 이 옵션을 사용하십시오. 해당 이유에는 기존 게이트웨이 어플라이언스 또는 다중 VLAN 방화벽과 VLAN을 사용하는 경우가 포함됩니다. 일반적으로 대규모 배치 체계의 일부로 추가 VLAN을 주문하는 경우 VLAN을 포함할 팟(Pod)을 알고 있습니다. 그러면 이 옵션을 선택하십시오.

VLAN의 위치가 덜 중요하면 **데이터 센터별 주문** 옵션을 사용하십시오. 이 옵션은 다른 리소스를 클러스터링할 위치를 시드(seed)하려는 경우 최적입니다. 배치에서 네트워크 우선 전략(주문 서버 우선과 대조적)을 따르는 경우 이 옵션을 사용하여 새 데이터 센터에 사용자의 존재를 설정하면 최상의 경험을 제공할 수 있습니다. 요청한 VLAN은 선택한 데이터 센터의 모든 팟(Pod)에서 이행합니다. 이 옵션을 선택할 때 어떤 팟(Pod)이 선택될지 예상하지 마십시오.

사용 가능한 위치 옵션 중에서 현재 요구사항에 맞는 임의 위치를 사용하는 것이 가장 좋습니다.

### 복합 주문
{:#complex-orders-vlans}

포털 주문 환경에서는 주문당 하나의 VLAN 구성만 주문할 수 있습니다. 구성은 원하는 네트워크, 위치 옵션 및 수량으로 구성됩니다. API를 통해 단일 주문에서 여러 VLAN 구성을 주문할 수 있지만 각 구성 수량은 1로 제한됩니다. 즉, 제공되는 각 VLAN 구성은 개별적으로 이행됩니다. 따라서 각 구성에서 데이터 센터 위치 옵션을 활용하는 경우 해당 데이터 센터의 여러 다른 팟(Pod)에 각 VLAN을 지정할 수 있습니다.

### 용량에 관한 참고
{:#note-about-capacity}

선택한 위치의 용량 제한사항 때문에 VLAN 주문이 방지될 수 있습니다. 이 경우 해당 위치에서 VLAN을 주문하려는 모든 사용자에게 영향을 미치며, 지원이 제공되지 않습니다. 가능하면 다른 데이터 센터에 존재를 설정하고 [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)을 이용하도록 권장합니다. 위치 요구사항이 유연한 경우 VLAN을 주문할 때 구체적이지 않은 위치를 사용하는 것이 가장 좋습니다. 그러면 VLAN 할당 시 유연성이 증가되기 때문입니다. 또한 이전에 시도한 위치의 VLAN 용량을 나중에 사용할 수 있게 됩니다.


## 프리미엄 VLAN 취소
{:#canceling-premium-vlans}

프리미엄 VLAN을 제거할 준비가 되면 계정의 VLAN 목록(위의 VLAN 관리 참조)에서 VLAN을 찾고 해당 항목의 "X" 아이콘을 클릭하여 취소 프롬프트를 시작하십시오.

프리미엄 VLAN은 다른 제품에서 사용 중인 경우 취소할 수 없습니다. 다음과 같이 사용하면 취소할 수 없습니다.

  * VLAN을 서버의 홈으로 직접 지정(트렁킹과 대조적).
  * 보조 서브넷이 VLAN 또는 VLAN의 IP 주소로 라우팅.
  * 전체 VLAN에 서비스를 제공하는 방화벽 제품. 예를 들어 비전용 하드웨어 방화벽은 제외됩니다.
  * 자동 스케일링 그룹과 연관.
  * 서버에 트렁킹됨(나중에 변경될 예정).

또한 일부 제품과 기능에서는 VLAN **취소를 방지하지 않지만** VLAN 제거의 영향을 받습니다. 여기에는 다음이 포함됩니다. 

  * 가상 라우터 어플라이언스에서 보호합니다. 우회 여부에 상관없이 VLAN 연관이 제거됩니다.

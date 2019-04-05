---

copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-28"

keywords: VLAN Spanning VLAN, Default values, VLAN Spanning

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}


# VLAN 스패닝
{: #vlan-spanning}

VLAN Spanning을 사용하면 계정의 모든 디바이스가 디바이스에 지정된 VLAN과 상관없이 사설 네트워크를 통해 서로 통신할 수 있습니다.
{: #shortdesc}

## VLAN Spanning 이해
{: #understanding-vlan-spanning}


{{site.data.keyword.Bluemix}}에서 VLAN Spanning은 여러 다른 용도로 사용할 수 있으며 디바이스 통신에 영향을 미칩니다. 시작하기 전에 VLAN Spanning의 기본에 관해 자세히 알아보려면 다음 정보를 검토하십시오.
{: shortdesc}

### VLAN Spanning 작동 방식
{: #how-vlan-spanning-works}

VLAN Spanning을 사용하도록 설정하면 라우팅된 모든 트래픽이 계정에 있는 모든 사설 VLAN의 모든 사설 서브넷 간에 이동할 수 있습니다. 따라서 라우팅된 트래픽의 글로벌 통신이 필요한 비즈니스 요구사항에 맞게 서비스를 제공합니다. 예를 들어 동일한 VLAN에 있는지 아니면 서로 다른 VLAN에 있는지에 상관없이 두 개 이상의 사설 서브넷에 있는 디바이스가 통신해야 하는 경우 VLAN Spanning을 사용하도록 설정하십시오.

Spanning을 사용하도록 설정하면 전체 계정에 영향을 미칩니다. VLAN Spanning에서 서브넷, VLAN 또는 디바이스를 제외할 수 없습니다. 현재 사설 서브넷만 사용하여 서버를 역할이나 티어로 분리하는 경우 VLAN Spanning을 사용하도록 설정하면 해당 분리가 제거됩니다.
{:note}

### 기본값
{: #vlan-spanning-default-values}

기본적으로 VLAN Spanning은 사용 안함으로 설정됩니다. 두 개의 서로 다른 사설 서브넷에 있는 디바이스는 동일한 VLAN에 있든 아니면 서로 다른 VLAN에 있든 서로에게 IP 트래픽을 보낼 수 없습니다.

### 일반적으로 VLAN Spanning이 필요한 서비스
{: #vlan-spanning-services}

상황에 맞게 VLAN Spanning을 설정하는 데 유용한 특정 튜토리얼을 사용할 수 있습니다. [기타 리소스](/docs/infrastructure/vlans?topic=vlans-other-resources-for-vlan-spanning)에 대한 링크를 참조하십시오.


## VLAN Spanning 관리
{: #manage-vlan-spanning}

계정에 VLAN Spanning을 사용하거나 사용하지 않게 설정할 수 있습니다.
{: shortdesc}

계정 설정을 업데이트하려면 다음 단계를 따르십시오.

  1. 브라우저에서 [{{site.data.keyword.Bluemix_notm}} 콘솔 ![외부 링크 아이콘](../../icons/launch-glyph.svg "외부 링크 아이콘")](https://{DomainName}/){: new_window}을 열고 계정에 로그인하십시오.
  2. 메뉴에서 **인프라**를 선택하십시오. 고객 포털이 열립니다.
  3. 고객 포털 탐색에서 **네트워크 > IP 관리> VLAN**을 선택하십시오.
  4. **스팬** 탭을 선택하여 VLAN Spanning 섹션에 액세스하십시오.
  5. 원하는 대로 **설정** 또는 **해제** 단일 선택 단추를 선택하여 VLAN Spanning을 각각 사용하거나 사용하지 않게 설정하십시오.

단시간 내에 VLAN Spanning을 전환하면 애플리케이션이 지연될 수 있습니다.
{:note}

업데이트 요청은 처리하는 데 최대 15분이 걸릴 수 있습니다. 변경 확인이 화면에 표시됩니다. 이전 단계를 반복하여 언제든 VLAN Spanning 설정을 업데이트할 수 있습니다.

---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 자동 VLAN 업그레이드
{:#upgrading-automatic-vlan}

자동 VLAN에 맞게 솔루션을 빌드한 다음 나중에 프리미엄 VLAN의 기능을 사용하도록 결정하면 업그레이드할 수 있습니다. 업그레이드는 되돌릴 수 없습니다. VLAN은 프리미엄 VLAN이 되고 취소할 때까지 계정에 남아 있습니다. 취소하면 회수됩니다.

VLAN을 항상 업그레이드할 수 있는 것은 아닙니다. VLAN 용량 제한사항이 여전히 적용됩니다.

현재 업그레이드는 API를 통해서만 가능합니다. 이 작업을 수행하는 데 다음 두 방법을 사용할 수 있습니다.

  1. `SoftLayer_Product_Order.placeOrder`를 활용하여 주문합니다.
  2. `SoftLayer_Network_Vlan.upgrade` 바로 가기 인터페이스를 활용합니다.

## 주문하기
{:#place-vlan-order}

  1. 일반 프리미엄 VLAN과 비슷하게 주문을 생성합니다. 이때 정확한 패키지와 가격을 지정합니다.
  1. 새 프리미엄 VLAN을 주문할 때 필요한 `위치`와 `routerId` 특성을 제거합니다.
  1. `id` 특성을 추가하고 업그레이드할 VLAN의 `SoftLayer_Network_Vlan.id` 값으로 채웁니다.

## 바로 가기 인터페이스
{:#vlan-shortcut-interface}

업그레이드할 VLAN의 `SoftLayer_Network_Vlan.id` 값으로 호출을 초기화하여 기존 VLAN에 대해 [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) 오퍼레이션을 실행하십시오. 그러면 VLAN의 적절한 패키지와 가격 정보를 찾고 업그레이드를 수행하는 데 필요한 주문을 합니다. 이 메소드를 사용하면 계정이 자동 주문 승인에 적합한 경우에만 VLAN 업그레이드를 주문할 수 있습니다. 

자세한 정보는 [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/)의 API 문서를 참조하십시오.

## 다음에 실행되는 작업
{:#upgrade-vlan-what-happens-next}

성공적으로 주문하고 나면 바로 VLAN이 프리미엄 VLAN으로 전환됩니다.

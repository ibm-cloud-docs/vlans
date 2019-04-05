---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 升級自動 VLAN
{:#upgrading-automatic-vlan}

如果您建置了關於自動 VLAN 的解決方案，後來決定想要讓它有超值 VLAN 的功能，那麼您可以將它升級。升級無法回復。VLAN 會變成超值 VLAN，並且會維持在您的帳戶上，直到取消為止；取消時將會收回。

並不一定可以升級 VLAN。VLAN 容量限制仍然適用。

在目前，只能透過 API 進行升級。有兩種方法可以這麼做：

  1. 利用 `SoftLayer_Product_Order.placeOrder` 下訂單。
  2. 利用 `SoftLayer_Network_Vlan.upgrade` 捷徑介面。

## 下訂單
{:#place-vlan-order}

  1. 類似一般超值 VLAN 般建構訂單，尤其要使用正確的套件和定價。
  1. 移除訂購新的超值 VLAN 時必要的 `location` 及 `routerId` 內容。
  1. 新增 `id` 內容，並用要升級之 VLAN 的 `SoftLayer_Network_Vlan.id` 值移入其中。

## 捷徑介面
{:#vlan-shortcut-interface}

藉由使用要升級之 VLAN 的 `SoftLayer_Network_Vlan.id` 值起始設定呼叫，針對現有的 VLAN 執行 [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) 作業。這會找到適合 VLAN 的套件及定價資訊，然後送出必要的訂單以執行升級。使用此方法，VLAN 升級訂單只會在您的帳戶符合自動訂單核准時才會送出。

如需詳細資料，請參閱 [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) 的 API 文件。

## 後續情形
{:#upgrade-vlan-what-happens-next}

成功下訂單之後不久，VLAN 便會轉移成超值 VLAN。

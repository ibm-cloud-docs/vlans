---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 自動 VLAN のアップグレード
{:#upgrading-automatic-vlan}

自動 VLAN を基にソリューションを構築した後にプレミアム VLAN の機能を導入したくなった場合には、アップグレードできます。アップグレードは元に戻せない操作です。VLAN はプレミアム VLAN になり、キャンセルするまではアカウントに存在します。キャンセルすると、VLAN は回収されます。

VLAN のアップグレードは常に可能なわけではありません。やはり VLAN 容量制限が適用されます。

当面の間、API を使用する以外にアップグレードする方法はありません。次の 2 つの方法でアップグレードできます。

  1. `SoftLayer_Product_Order.placeOrder` を使用して注文します。
  2. `SoftLayer_Network_Vlan.upgrade` ショートカット・インターフェースを使用します。

## 注文
{:#place-vlan-order}

  1. 通常のプレミアム VLAN と同じように注文します。正確なパッケージと価格が表示されます。
  1. 新しいプレミアム VLAN を注文するときに必要な `location` プロパティーと `routerId` プロパティーは除外します。
  1. `id` プロパティーを追加し、アップグレードする VLAN の `SoftLayer_Network_Vlan.id` 値を設定します。

## ショートカット・インターフェース
{:#vlan-shortcut-interface}

[SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) 操作を既存の VLAN に対して実行します。そのためには、アップグレードする VLAN の `SoftLayer_Network_Vlan.id` 値を設定して呼び出しを初期化します。これにより、対象 VLAN に該当するパッケージと価格の情報が検出され、アップグレードを実行するために必要な注文が行われます。この方法を使用して VLAN アップグレードを注文できるのは、アカウントに自動注文の承認資格がある場合だけです。

詳しくは、[SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) の API 資料を参照してください。

## 結果
{:#upgrade-vlan-what-happens-next}

注文の発行が成功するとすぐに、VLAN がプレミアム VLAN に移行されます。

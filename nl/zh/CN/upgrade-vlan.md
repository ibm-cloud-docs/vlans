---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# 升级自动 VLAN
{:#upgrading-automatic-vlan}

如果围绕着自动 VLAN 构建解决方案，并且稍后决定希望它具有高端 VLAN 的功能，那么可以进行升级。升级不可逆。VLAN 成为高端 VLAN 后，会保留在您的帐户上，直至取消为止；在取消时将进行回收。

升级 VLAN 并非总是可行。仍存在 VLAN 容量限制。

此时，只能通过 API 进行升级。执行此操作的两种可用方法为：

  1. 利用 `SoftLayer_Product_Order.placeOrder` 下订单。
  2. 利用 `SoftLayer_Network_Vlan.upgrade` 快捷接口。

## 下订单
{:#place-vlan-order}

  1. 构造类似于典型高端 VLAN 的订单；尤其是使用正确的包和定价。
  1. 除去订购新的高端 VLAN 时所需的 `location` 和 `routerId` 属性。
  1. 添加 `id` 属性，并使用要升级的 VLAN 的 `SoftLayer_Network_Vlan.id` 值进行填充。

## 快捷接口
{:#vlan-shortcut-interface}

通过使用要升级的 VLAN 的 `SoftLayer_Network_Vlan.id` 值初始化调用，针对现有 VLAN 执行 [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) 操作。这将针对 VLAN 查找相应的包和定价信息，并下必需的订单以执行升级。使用此方法，仅在帐户满足自动订单核准资格时才会下 VLAN 升级订单。

请参阅 [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) 的 API 文档以获取更多详细信息。

## 后续操作
{:#upgrade-vlan-what-happens-next}

在成功下订单后，VLAN 将很快转移为高端 VLAN。

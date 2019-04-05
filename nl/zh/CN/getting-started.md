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

# VLAN 入门
{:#getting-started-with-vlans}

{{site.data.keyword.cloud}} 使用虚拟局域网 (VLAN) 来隔离公用和专用网络上的广播流量。VLAN 可根据需要进行分配，以满足其他产品的要求。例如，如果针对您在其中尚无存在性的数据中心下计算订单，那么您将自动收到一个 VLAN。通常，将在先前分配的 VLAN 中下针对相同数据中心的其他计算订单（未指定网络需求）。对于自动分配的所有 VLAN，当您的资源不再需要这些 VLAN 时，也会自动除去这些 VLAN。

VLAN 特定于在 IBM Cloud 数据中心中使用的路由器，并且数据中心包含针对公用和专用网络的多个路由器。因此，可以在单个数据中心中分配多个 VLAN。还可以订购其他 VLAN 以构造更复杂的网络拓扑；通常，与[虚拟路由器设备](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance)相结合。

我们将购买的 VLAN 称为**高端 VLAN**，并将由 {{site.data.keyword.cloud}} 自动管理的 VLAN 称为**自动 VLAN**。在[关于 VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans) 中了解有关 VLAN 如何运行的更多信息。


## 管理 VLAN
{:#managing-vlans}

遵循以下步骤以查看帐户上的 VLAN。

  1. 打开 [IBM Cloud 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/){: new_window}，然后登录到您的帐户。
  2. 在菜单中，选择**基础架构**。
  3. 在客户门户网站导航中，选择**网络 > IP 管理 > VLAN**。

VLAN 列表显示有关 VLAN 的信息，并且可用于访问每个 VLAN 及其关联设备或子网。

### 了解 pod 与数据中心选择
{:#pod-vs-datacenter-selection}

关于在何处订购 VLAN 的选项支持不同的需求和约束。此部分概述可能选择一个选项而不是另一个选项的原因。

**按 Pod 订购**选项允许您指定在其中需要 VLAN 的确切 pod（以及路由器）。如果有明确理由要求 VLAN 存在于该 pod 中，请使用此选项。其理由包括将 VLAN 用于现有网关设备或多 VLAN 防火墙。通常，如果作为较大部署方案的一部分订购其他 VLAN，那么您知道自己希望 VLAN 所在的 pod。如果是这样，请选择此选项。

在 VLAN 的位置较不重要时，使用**按数据中心订购**选项。在想要将用于对其他资源建立集群的位置设为种子值时，此选项最适合。如果部署遵循网络优先策略（而不是订购服务器优先），那么使用此选项确定您在新数据中心内的存在性可提供最佳体验。请求的 VLAN 由所选数据中心内的任何 pod 实现；选择此选项时，针对将选择哪个 pod 不要设定预期。

最好使用适合您当前需求的最不具体的可用位置选项。

### 复杂订单
{:#complex-orders-vlans}

门户网站订购体验仅支持每个订单订购单个 VLAN 配置。配置由所需的网络、位置选项和数量组成。虽然可通过 API 在单个订单中订购多个 VLAN 配置，但是每个配置数量限制为 1。这意味着单独实现每个提供的 VLAN 配置。因此，如果每个配置利用数据中心位置选项，那么可将每个 VLAN 分配到该数据中心内的不同 pod。

### 有关容量的注释
{:#note-about-capacity}

由于所选位置中的容量限制，可能会阻止订购 VLAN 的尝试。如果遇到此情况，这会影响尝试订购该位置中的 VLAN 的所有用户；没有解决办法。如果可能，我们鼓励您在另一个数据中心内建立存在性，并考虑利用 [VLAN 生成](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)。如果位置需求灵活，那么在订购 VLAN 时最好使用最不具体的位置选项，因为这在分配 VLAN 时可以更灵活。此外，先前尝试过的位置中的 VLAN 容量可能在以后变为可用。


## 取消高端 VLAN
{:#canceling-premium-vlans}

准备好除去高端 VLAN 时，请在您帐户的 VLAN 列表中找到该 VLAN（请参阅上面的“管理 VLAN”），然后单击条目中的“X”图标以启动取消提示。

如果其他产品正在使用高端 VLAN，那么无法取消这些 VLAN。以下使用情况会阻止取消：

  * 服务器直接位于 VLAN 上（而不是中继）。
  * 辅助子网路由到 VLAN 或 VLAN 上的 IP 地址。
  * 防火墙产品处理整个 VLAN。这就排除了非专用硬件防火墙，等等。
  * 关联到自动缩放组。
  * 中继到服务器（这将在未来更改）。

此外，某些产品和功能**不会阻止取消** VLAN，但是在除去该 VLAN 后将受到影响。这些包括：

  * 由虚拟路路由器设备进行保护。无论是否绕过，都将除去 VLAN 关联。

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

# 关于 VLAN
{:#about-vlans}

VLAN 是将流量定向到资源的中心。您可能从不需要直接与任何 VLAN 交互，因为它们是自动进行管理的：它们根据需要进行分配并在不需要时除去。

VLAN 是网络概念。它允许您在 [OSI 模型 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://en.wikipedia.org/wiki/OSI_model) 第 2 层级别_数据链路层_创建广播域。VLAN 提供一种包识别方法，并且允许同一物理设备上多个工作负载共存。有关 VLAN 的更多信息，请参阅[本文章 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://en.wikipedia.org/wiki/Virtual_LAN)。

## VLAN 的类型
{:#types-of-vlans}

存在两种不同类型的 VLAN，{{site.data.keyword.cloud}} 将它们称为**自动**和**高端**。每种类型都承担不同的角色，根据您的需求，了解其差别非常重要。

### 自动 VLAN
{:#automatic-vlans}

自动 VLAN 由 {{site.data.keyword.cloud}} 自动管理；根据需要进行分配和除去以满足订购的其他产品的需求。通常每个路由器有一个自动 VLAN。自动 VLAN 关联到订购的服务器，而无需选择特定 VLAN。无法订购或取消自动 VLAN，因为它们仅在系统确定需要它们时存在于帐户上，并且将在系统确定不再需要它们时除去。

### 高端 VLAN
{:#about-premium-vlans}

通过订购 VLAN 获取高端 VLAN。请参阅[订购高端 VLAN](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans) 以获取指示信息。在明确取消之前，高端 VLAN 将保留在帐户上。在容量限制范围内，您可以订购所需任意数量的高端 VLAN。如果容量不可用，请寻求其他 pod 或数据中心内的 VLAN。

高端 VLAN 的重要区别在于，它们不是自动选择用于满足服务器订单的。必须在服务器订购过程中明确选择高端 VLAN 以使服务器驻留其中。请参阅[常见问题](/docs/infrastructure/vlans?topic=vlans-vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-)以获取有关 VLAN 选择的指示信息。


## VLAN 标识
{:#vlan-identification}

VLAN 存在于 IBM Cloud 数据中心内的路由器上。每个 VLAN 可通过唯一编号、路由器和数据中心位置组合进行标识。例如，位于数据中心 `SJC01` 中路由器 `fcr02` 上的公用 `VLAN 829` 由 `sjc01.fcr02.829` 标识。位于数据中心 `AMS01` 中路由器 `bcr01` 上的专用 VLAN 2234 由 `ams01.bcr01.2234` 标识。


## VLAN 和子网
{:#vlans-subnets}

VLAN 可包含一个或多个子网。与 VLAN 类似，在设备需要 IP 地址时自动添加和除去某些子网。[子网和 IP](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips) 中进一步详述哪些子网可存在及其运行方式。


## 在 VLAN 中通信
{:#communication-within-vlans}

VLAN 上的所有资源可通信，但是并不意味着缺省情况下它们将通信。请务必记住，VLAN 位于 OSI 模型第 2 层构造上，而子网/IP 位于第 3 层构造上。每一层以不同的方式进行通信。不同 VLAN 中的资源（无论是在公用子网还是专用网络上）无法通过第 2 层方法相互通信。

### 公用网络上 VLAN 中的通信
{:#communication-within-vlans-public}

公用网络上资源之间的通信无固有限制，无论是位于 {{site.data.keyword.cloud}} 公用网络基础架构中的一个或多个 VLAN 上还是因特网上。可通过引入防火墙或网关设备来添加限制。

### 专用网络上 VLAN 中的通信
{:#communication-within-vlans-private}

缺省情况下，仅同一子网中的计算可通信，即使多个子网位于同一 VLAN 中。但是，只要计算实例具有针对此 VLAN 上其他子网的路由条目，那么就可以与相同 VLAN 上的其他子网进行通信。管理需要跨专用子网进行通信的所有计算节点上的路由条目可能很麻烦。对于在相同 VLAN 中的所有计算上需要缺省通信的情况，请参阅 [VLAN 生成](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)。请注意，“VLAN 生成”具有广泛影响，应在启用前仔细审查。

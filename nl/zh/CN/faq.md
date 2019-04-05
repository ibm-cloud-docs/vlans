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

# 常见问题
{:#vlans-faqs}


## 是否可以将现有设备移至新的 VLAN？
{: faq}

现有设备可以移至其他 VLAN，但仅在请求移动时才移动。由于 VLAN 绑定到路由器，并且与每个路由器的连接取决于设备的物理位置，因此某些 VLAN 移动还可能需要重新定位物理位置。新的 VLAN 位于不同的数据中心时，始终需要重新定位物理位置，而将设备移至同一数据中心内的不同 VLAN 时，也可能需要这样做。进行此更改会中断网络连接，并且在连接移至新 VLAN 时，需要更改设备的 IP 地址。将设备移至新的 VLAN 时，我们要求允许充分的规划，因为在移动过程中机器将处于脱机状态。


## 在订购设备时是否可以指定设备要使用的 VLAN？
{: faq}

可以，在订购过程中可以选择一个特定的 VLAN。订购设备时，此选项在订购表单的末尾提供。先选择专用 VLAN，然后选择公用 VLAN。另请注意，针对每个 VLAN 提供一个子网选择器；此选择为**可选**。如果您有理由仅选择一个子网，可以这样做，因为选择缺乏可用 IP 地址的子网将对设备的实现造成负面影响（请参阅[子网常见问题](/docs/infrastructure/subnets?topic=subnets-subnets-faq)以获取更多详细信息）。

务必注意的是，选中的 VLAN 必须与设备位于同一个数据中心。我们无法将设备分配给位于其他数据中心的 VLAN。


## 可将多少个设备分配给单个 VLAN？
{: faq}

当前，任何时候与单个 VLAN 相关联的设备数量不存在任何限制；但是，硬件防火墙与 VLAN 关联时，防火墙的类型可能会限制位于 VLAN 上的设备数量。


## 可将哪些类型的设备分配给 VLAN？
{: faq}

任何具有网络连接的设备都将与 VLAN 关联。专用服务器同时具有公用和专用网络连接，因此您将看到同时与公用和专用 VLAN 关联的设备。

## 如何将 VLAN 中继到服务器？
{: faq}

VLAN 只能通过使用 API 中继到裸机服务器；无门户网站界面适用于此活动。
有关作为干线管理 VLAN 的更多信息，请参阅以下 API 文档链接。
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## 在订购 VLAN 时，我被告知无任何可用的 VLAN，这意味着什么？
{: faq}

请参阅[有关容量的注释](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity)。


## 为什么我的设备无法与相同专用 VLAN 上的其他设备进行通信？
{: faq}

如果每个服务器位于不同子网上，那么缺省情况下，它们将无法通过 IP 地址进行通信。在技术上，服务器可使用 OSI 模型第 2 层方法进行通信，因为它们位于相同 VLAN 上（第 2 层构造）。要使因特网协议 (IP)（也称为第 3 层）通信生效，您可以在每台服务器上针对尝试与之通信的子网添加路由（每台服务器上的路由不同），或者启用 [VLAN 生成](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)。请注意，[VLAN 生成](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)具有其他影响，因此在决定启用前，请详细审查功能。


## 如果需要同一 VLAN 中不同专用子网上的设备缺省情况下可通信，但是不想要启用 VLAN 生成，那么我有哪些选项？
{: faq}

考虑到 {{site.data.keyword.cloud}} 会根据需要自动分配和除去主子网，我们明白管理服务器上的路由很麻烦。我们也明白 [VLAN 生成](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)并非总是可行。如果您具有受此行为阻碍的大型部署，那么只能在在[高端 VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans) 上请求容纳主子网。将针对此子网收费，并且费用可能根据请求的不同而不同。我们将逐个情况（不是按帐户考虑，而是按每个请求）自行决定是同意还是拒绝此类请求。遵循这些指示信息以请求定制大小的主子网：

  1. 打开 [IBM Cloud 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/){: new_window}，然后登录到您的帐户。
  1. 在菜单中，选择**经典基础架构**。 
  1. 在“经典基础架构”导航菜单中，选择**网络 > IP 管理 > VLAN**。
  1. 订购高端 VLAN（如果需要）。请参阅[订购高端 VLAN](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans)。
  1. 通过在菜单中导航至**支持 > 添加凭单**来开具凭单。
    - 主题：“专用网络问题”或“公用网络问题”
    - 标题：“大型主子网请求”
    - 详细信息：使用 datacenter.router.vlan 表示法指定希望子网位于的高端 VLAN（例如，ams03.bcr01.1234）。然后，通过 CIDR 表示法指定所需的子网大小（例如，/25）。指示计划购买的服务器数量以及时间段。此外，阐述在没有请求的子网时会对您的使用造成什么阻碍。请详细阐述阻碍情况，因为此输入可帮助我们评估对平台的改进。不会考虑子网的其他属性，因此无需进一步规范。

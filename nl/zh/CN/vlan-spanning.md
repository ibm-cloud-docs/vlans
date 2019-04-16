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


# VLAN 生成
{: #vlan-spanning}

VLAN 生成支持帐户中的所有设备通过专用网络相互通信，而不管设备分配给哪个 VLAN。
{: #shortdesc}

## 了解 VLAN 生成
{: #understanding-vlan-spanning}


在 {{site.data.keyword.Bluemix}} 中，VLAN 生成可用于多个不同目的并且影响设备通信。要在开始前了解有关 VLAN 生成的更多基础知识，请查看以下信息。
{: shortdesc}

### VLAN 生成的工作方式
{: #how-vlan-spanning-works}

通过启用 VLAN 生成，所有路由的流量能够在帐户的所有专用 VLAN 上的所有专用子网之间传输。这满足需要路由的流量进行全局通信的业务需求。例如：如果位于多个专用子网上的设备需要进行通信，无论是位于相同还是不同 VLAN 上，都请启用 VLAN 生成。

在启用生成时，会影响整个帐户。您无法从 VLAN 生成中免除任何子网、VLAN 或设备。如果当前仅依赖于专用子网以将服务器分隔到角色或层，那么启用 VLAN 生成将除去此隔离。
{:note}

### 缺省值
{: #vlan-spanning-default-values}

缺省情况下，禁用了 VLAN 生成。位于两个不同专用子网上（无论是相同还是不同 VLAN 上）的设备将无法相互发送 IP 流量。

### 通常需要 VLAN 生成的服务
{: #vlan-spanning-services}

提供了具体教程以帮助您针对自己的情况设置 VLAN 生成。请访问指向[其他资源](/docs/infrastructure/vlans?topic=vlans-other-resources-vlan-spanning)的链接。


## 管理 VLAN 生成
{: #manage-vlan-spanning}

您可以针对帐户启用或禁用 VLAN 生成。
{: shortdesc}

要更新帐户设置，请执行以下步骤：

  1. 在浏览器中，打开 [{{site.data.keyword.Bluemix_notm}} 控制台 ![外部链接图标](../../icons/launch-glyph.svg "外部链接图标")](https://{DomainName}/){: new_window}，然后登录到您的帐户。
  2. 在菜单中，选择**基础架构**。此时将打开客户门户网站。
  3. 在客户门户网站导航中，选择**网络 > IP 管理 > VLAN**。
  4. 选择**生成**选项卡，以访问“VLAN 生成”部分。
  5. 根据需要选择**开启** 或**关闭**单选按钮以分别启用或禁用 VLAN 生成。

在短时间内切换 VLAN 生成可能导致延迟应用。
{:note}

处理更新请求可能最长需要 15 分钟。将在屏幕上显示更改确认。您可以通过重复上述步骤，随时更新 VLAN 生成设置。

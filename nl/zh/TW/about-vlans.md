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

# 關於 VLAN
{:#about-vlans}

VLAN 是將資料流量導向資源的核心。您可能永遠不會需要直接與任何 VLAN 互動，因為它們的管理是自動的：它們會在需要時指派，不需要時移除。

VLAN 是一個網路概念。它容許您在 [OSI 模型 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://en.wikipedia.org/wiki/OSI_model) 第 2 層的層次建立廣播網域。VLAN 提供一個方法以進行封包識別，並且容許多個工作負載同時存在於相同的實體設備上。如需 VLAN 的相關資訊，請參閱[本文章 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://en.wikipedia.org/wiki/Virtual_LAN)。

## VLAN 的類型
{:#types-of-vlans}

有兩種不同類型的 VLAN，{{site.data.keyword.cloud}} 將其稱為**自動**和**超值**。他們各扮演不同的角色，且視您的需要而定，瞭解它們的差異很重要。

### 自動 VLAN
{:#automatic-vlans}

自動 VLAN 是由 {{site.data.keyword.cloud}} 自動管理；視需要指派及移除以完成您訂購之其他產品的需要。通常每台路由器會有一個自動 VLAN。自動 VLAN 與訂購時未選取特定 VLAN 的伺服器相關聯。無法訂購或取消自動 VLAN，因為它們只在我們的系統判斷有需要時才會存在於您的帳戶上，並在我們的系統判斷不再需要時移除。

### 超值 VLAN
{:#about-premium-vlans}

超值 VLAN 會藉由訂購 VLAN 來獲得。如需指示，請參閱[訂購超值 VLAN](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans)。超值 VLAN 會維持在您的帳戶上，直到明確取消為止。您可以訂購任意數量的超值 VLAN，但要遵循容量限制。當容量無法使用時，請尋求另一個 Pod 或資料中心裡的 VLAN。

超值 VLAN 的一項重要區別，在於它們不會自動選取以完成伺服器訂單。超值 VLAN 必須在伺服器訂購處理程序期間明確地選取，其上才會有伺服器存在。如需關於 VLAN 選取的指示，請參閱[常見問題](/docs/infrastructure/vlans?topic=vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-)。


## VLAN 識別
{:#vlan-identification}

VLAN 存在於 IBM Cloud 資料中心的路由器上。每一個 VLAN 都是透過唯一的號碼、路由器及資料中心位置組合所識別。例如，公用的 `VLAN 829` 位在資料中心 `SJC01` 的路由器 `fcr02` 上，而會識別為 `sjc01.fcr02.829`。專用的 VLAN 2234 位於資料中心 `AMS01` 內的路由器 `bcr01` 上，識別為 `ams01.bcr01.2234`。


## VLAN 及子網路
{:#vlans-subnets}

VLAN 可以包含一個以上的子網路。就像 VLAN，部分子網路會在裝置需要 IP 位址時自動新增及移除。什麼子網路可以存在，以及它們如何運作，會進一步詳述於[子網路及 IP](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips)。


## VLAN 內的通訊
{:#communication-within-vlans}

VLAN 上的所有資源都可以通訊，但那並不表示它們依預設便會通訊。請務必記住，VLAN 是 OSI 模型第 2 層的建構，子網路/IP 則是第 3 層的建構。每一層的通訊發生的情況不同。不同 VLAN 中的資源，不論是在公用還是專用網路上，都無法透過第 2 層方法彼此通訊。

### 公用網路上之 VLAN 內的通訊
{:#communication-within-vlans-public}

公用網路（不論是在 {{site.data.keyword.cloud}} 公用網路基礎架構內的一個以上 VLAN 還是在網際網路）上的資源之間通訊沒有固有的限制。您可以加入防火牆或 Gateway Appliance 來新增限制。

### 專用網路上之 VLAN 內的通訊
{:#communication-within-vlans-private}

依預設，只有相同子網路內的運算可以通訊，即使是多個子網路位於相同 VLAN 也一樣。不過，只要運算實例有該 VLAN 上其他子網路的路徑項目，便可以與相同 VLAN 上的其他子網路通訊。在需要跨越專用子網路通訊的所有運算節點上管理路徑項目可能很麻煩。針對在相同 VLAN 內所有運算之間需要預設通訊的狀況，請參閱 [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)。請注意，VLAN Spanning 有廣泛的可能影響，在啟用之前應該要小心檢閱。

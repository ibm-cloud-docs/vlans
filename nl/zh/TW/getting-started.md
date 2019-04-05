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

# 開始使用 VLAN
{:#getting-started-with-vlans}

{{site.data.keyword.cloud}} 使用虛擬區域網路 (VLAN) 來隔離公用及專用網路上的廣播資料流量。VLAN 會視需要指派，以完成其他供應項目。例如，如果您針對還沒有據點的資料中心送出運算訂單，您會自動收到 VLAN。對相同資料中心的其他運算訂單，不會指定網路需求，通常會在先前已指派的 VLAN 中送出。被自動指派的所有 VLAN 也會在您的資源不再需要它們時移除。

VLAN 是 IBM Cloud 資料中心使用之路由器所特有，且資料中心會包含公用和專用網路的多台路由器。因此，可以在單一資料中心內指派多個 VLAN。也可以訂購額外的 VLAN，以建構更複雜的網路拓蹼；通常是與 [Virtual Router Appliance](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance) 一起。

我們將購買的 VLAN 稱為**超值 VLAN**，而由 {{site.data.keyword.cloud}} 自動管理的 VLAN 則稱為**自動 VLAN**。在[關於 VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans) 中進一步瞭解 VLAN 的運作方式。


## 管理 VLAN
{:#managing-vlans}

請遵循下列步驟來檢閱您帳戶上的 VLAN。

  1. 開啟 [IBM Cloud 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/){: new_window}，並登入帳戶。
  2. 在功能表中，選取**基礎架構**。
  3. 在「客戶入口網站」導覽中，選取**網路 > IP 管理 > VLAN**。

VLAN 清單會顯示 VLAN 的相關資訊，並提供對每一個 VLAN 的存取，以及相關聯的裝置或子網路。

### 瞭解 Pod 與資料中心的選取
{:#pod-vs-datacenter-selection}

在何處訂購 VLAN 的選項為不同的需要及限制做準備。本節彙總您可能選取一個選項而不選取另一個選項的原因。

**依 Pod 訂購**選項容許您指定您需要 VLAN 的確切 Pod（以及因而指定路由器）。如果您有特定的原因需要 VLAN 存在於該 Pod，請使用這個選項。這樣做的原因包括使用 VLAN 搭配現有的 Gateway Appliance 或多 VLAN 防火牆。通常，如果您在較大的部署計劃當中訂購額外的 VLAN，您會知道您要 VLAN 位於哪個 Pod。若是如此，請選擇這個選項。

當 VLAN 的位置較不重要時，請使用**依資料中心訂購**選項。這個選項最適合您要以某個位置為根據地，且將在該處叢集放置其他資源的情況。如果您的部署遵循網路優先的策略（與訂購伺服器優先相反），那麼使用這個選項在新資料中心裡建立據點，會提供最佳的體驗。您所要求的 VLAN 會由所選取資料中心裡的任何 Pod 完成；選擇這個選項時請勿預期將選取哪個 Pod。

最好使用符合現行需要的可用位置選項中，最不特定的選項。

### 複雜訂單
{:#complex-orders-vlans}

入口網站訂購體驗只用於每張訂單訂購單一 VLAN 配置。配置包含想要的網路、位置選項，以及數量。雖然可以透過 API 在單一訂單中訂購多個 VLAN 配置，但每項配置數量限制為 1。這表示，所提供的每個 VLAN 配置都是獨立完成。因此，如果每個配置利用資料中心位置選項，則每個 VLAN 可以指派給該資料中心內的不同 Pod。

### 關於容量的附註
{:#note-about-capacity}

試圖訂購 VLAN 時，可能因為所選取位置中的容量限制而無法完成。如果發生此情況，它會影響嘗試在該位置訂購 VLAN 的所有使用者；沒有任何資源可用。可能的話，我們鼓勵您在另一個資料中心建立據點，並考慮利用 [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)。如果您的位置需要是彈性的，訂購 VLAN 時最好使用最不特定的位置選項，因為這允許配置 VLAN 時有更大的彈性。此外，先前嘗試位置的 VLAN 容量可能在之後變成可用。


## 取消超值 VLAN
{:#canceling-premium-vlans}

當您準備好移除超值 VLAN，請在帳戶的 VLAN 清單中找到該個 VLAN（請參閱上方的「管理 VLAN」），然後按一下項目內的 "X" 圖示，以起始取消提示。

超值 VLAN 如果正由其他產品使用中，便無法取消。下列使用情形會導致無法完成取消：

  * 伺服器直接位於 VLAN（而不是透過幹線連接）。
  * 次要子網路遞送至 VLAN 或 VLAN 上的 IP 位址。
  * 服務整個 VLAN 的防火牆產品。舉例來說，這不包括非專用硬體防火牆。
  * 與自動調整群組的關聯。
  * 透過幹線連接至伺服器（這在未來將會變更）。

此外，部分產品及特性**不會導致無法取消** VLAN，但會受到其移除影響。其中包括：

  * 受 Virtual Router Appliance 保護。不論是否略過，都將移除 VLAN 關聯。

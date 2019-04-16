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


# VLAN Spanning
{: #vlan-spanning}

VLAN Spanning 會讓帳戶上的所有裝置都透過專用網路彼此通訊，而不論裝置指派的 VLAN 為何。
{: #shortdesc}

## 瞭解 VLAN Spanning
{: #understanding-vlan-spanning}


在 {{site.data.keyword.Bluemix}} 中，VLAN Spanning 可以用於許多不同用途，且對於裝置通訊會有影響。若要進一步瞭解 VLAN Spanning 的基本觀念然後才開始使用，請檢閱下列資訊。
{: shortdesc}

### VLAN Spanning 的運作方式
{: #how-vlan-spanning-works}

藉由啟用 VLAN Spanning，您的所有遞送資料流量都能在所有專用子網路之間傳送，跨越帳戶上的所有專用 VLAN。這能夠滿足遞送資料流量需要廣域通訊的商業需要。例如：如果位於多個專用子網路（不論在相同還是不同的 VLAN 上）的裝置需要通訊，請啟用 VLAN Spanning。

啟用跨越之後，它會影響整個帳戶。您無法排除任何子網路、VLAN 或裝置不進行 VLAN Spanning。如果您目前完全依賴專用子網路，以將伺服器隔離成角色或層級，那麼啟用 VLAN Spanning 便不再需要該隔離。
{:note}

### 預設值
{: #vlan-spanning-default-values}

依預設，會停用 VLAN Spanning。位於兩個不同專用子網路上的裝置，不論是在相同還是不同的 VLAN 上，都將無法傳送 IP 資料流量給彼此。

### 一般需要 VLAN Spanning 的服務
{: #vlan-spanning-services}

有特定的指導教學可以協助您針對您的狀況設定 VLAN Spanning。請參閱[其他資源](/docs/infrastructure/vlans?topic=vlans-other-resources-vlan-spanning)的鏈結。


## 管理 VLAN Spanning
{: #manage-vlan-spanning}

您可以為您的帳戶啟用或停用 VLAN Spanning。
{: shortdesc}

若要更新您的帳戶設定，請遵循下列步驟：

  1. 從瀏覽器中，開啟 [{{site.data.keyword.Bluemix_notm}} 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/){: new_window}，並登入帳戶。
  2. 在功能表中，選取**基礎架構**。「客戶入口網站」隨即開啟。
  3. 在「客戶入口網站」導覽中，選取**網路 > IP 管理 > VLAN**。
  4. 選取**跨越**標籤，以存取 VLAN Spanning 區段。
  5. 視需要選取**開啟**或**關閉**圓鈕，以分別啟用或停用 VLAN Spanning。

在短時間內切換 VLAN Spanning 可能會導致應用程式延遲。
{:note}

更新要求最多可能需要 15 分鐘的時間處理。畫面上會顯示變更的確認。您隨時都可以重複先前的步驟，更新 VLAN Spanning 設定。

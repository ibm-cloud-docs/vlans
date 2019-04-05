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

# 常見問題
{:#vlans-faqs}


## 是否可以將現有裝置移至新的 VLAN？
{: faq}

現有裝置可以移至其他 VLAN，但只在要求移動時。因為 VLAN 關聯至路由器，而且與每一個路由器的連線取決於裝置的實體位置，所以部分 VLAN 移動也可能需要實體重新定位。這一律適用於新的 VLAN 位在不同的資料中心時，但也可能適用於將裝置移至相同資料中心內的不同 VLAN 時。進行這項變更會岔斷網路連線功能，而且在將連線移至新的 VLAN 時，需要變更裝置的 IP 位址。將裝置移至新的 VLAN 時，我們要求容許足夠的規劃，因為機器將會在移動期間離線。


## 訂購裝置時，是否有方法可以指定要用於裝置的 VLAN？
{: faq}

是，在訂購處理程序期間可以選取特定 VLAN。訂購裝置時，可以在訂單表格結尾提供此選項。選取後面接著公用 VLAN 的專用 VLAN。也請注意，會出現每個 VLAN 的子網路選取器；這個選取動作是**選用性的**。只有在有理由時才選取子網路，因為選取缺乏可用 IP 位址的子網路會對裝置的完成有負面影響（如需詳細資料，請參閱[子網路常見問題](/docs/infrastructure/subnets?topic=subnets-subnets-faq)）。

請務必注意，選取的 VLAN 必須位在與裝置相同的資料中心內。我們無法將裝置指派給位在不同資料中心內的 VLAN。


## 有多少裝置可以指派給單一 VLAN？
{: faq}

目前不限制任何時間與單一 VLAN 相關聯的裝置數目；不過，硬體防火牆與 VLAN 相關聯時，防火牆的類型可能會強制限制 VLAN 上的裝置數目。


## 哪些類型的裝置會指派給 VLAN？
{: faq}

任何具有網路連線的裝置都會與 VLAN 相關聯。專用伺服器同時具有公用及專用網路連線，因此您會看到與公用及專用 VLAN 相關聯的這些裝置。

## 如何讓 VLAN 成為伺服器的主幹？
{: faq}

VLAN 只能透過使用 API 而作為裸機伺服器的主幹；此活動沒有可用的入口網站介面。如需管理 VLAN 作為主幹的相關資訊，請參閱底下的 API 文件鏈結。
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## 訂購 VLAN 時，我被告知沒有任何可用的 VLAN，這是什麼意思？
{: faq}

請參閱[關於容量的附註](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity)。


## 我的裝置為何無法與相同專用 VLAN 上的裝置彼此通訊？
{: faq}

如果每部伺服器都在不同的子網路上，那麼依預設它們將無法透過 IP 位址通訊。技術上來說，您的伺服器可以使用 OSI 模型第 2 層的方法通訊，因為它們在相同的 VLAN（一項第 2 層的建構）。網際網路通訊協定 (IP)（也稱為第 3 層）通訊若要運作，您可以在每部伺服器上為試圖與其通訊的子網路新增路徑（路徑在每部伺服器上皆不同），或是啟用 [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)。請注意，[VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) 有額外的可能影響，因此請詳細檢閱特性，然後才決定啟用它。


## 如果我需要相同 VLAN 內不同專用子網路上的裝置能依預設通訊，但我不想要啟用 VLAN Spanning，我有什麼選項？
{: faq}

我們瞭解在伺服器上管理路徑很麻煩，考量到 {{site.data.keyword.cloud}} 視需要自動指派及移除主要子網路的話。我們也瞭解 [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) 不是永遠都可能進行。如果您有大型的部署受到此行為阻礙，可以只針對[超值 VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans) 要求通融的主要子網路。費用將會加到這個子網路，且可能會隨各個要求而變。我們將依每個案例斟酌要授與還是拒絕這樣的要求（不是依每個帳戶，而是依每個要求）。請遵循下列指示來要求專門指定大小的主要子網路：

  1. 開啟 [IBM Cloud 主控台 ![外部鏈結圖示](../../icons/launch-glyph.svg "外部鏈結圖示")](https://{DomainName}/){: new_window}，並登入帳戶。
  1. 在功能表中，選取**標準基礎架構**。 
  1. 在「標準基礎架構」導覽功能表中，選取**網路 > IP 管理 > VLAN**。
  1. 必要的話，訂購超值 VLAN。請參閱[訂購超值 VLAN](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans)。
  1. 在功能表中導覽至**支援 > 新增問題單**來開立問題單。
    - 主旨："Private Network Question" 或 "Public Network Question"
    - 標題："Large Primary Subnet Request"
    - 詳細資料：指定您想要在其上有子網路的超值 VLAN，並使用 datacenter.router.vlan 表示法（例如 ams03.bcr01.1234）。然後以 CIDR 表示法指定想要的子網路大小（例如 /25）。指出您計劃購買多少部伺服器，以及在什麼時段。此外，也請說明若無所要求的子網路，您的用量將會受到什麼樣的阻礙。請詳述您的狀況受阻礙的情形，因為這項輸入能協助我們評估對平台的改善功能。我們不會考量子網路的任何其他內容，因此不需要進一步的規格。

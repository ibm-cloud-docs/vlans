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


# VLAN スパンニング
{: #vlan-spanning}

VLAN スパンニングは、VLAN の割り当てに関係なく、アカウントのすべてのデバイスがプライベート・ネットワークを使用して相互通信できるようにします。
{: #shortdesc}

## VLAN スパンニングについて
{: #understanding-vlan-spanning}


{{site.data.keyword.Bluemix}} では、さまざまな目的に VLAN スパンニングを使用できます。また、VLAN スパンニングはデバイス通信に影響を与えます。作業を始める前に VLAN スパンニングの基本について理解するため、以下の情報に目を通してください。
{: shortdesc}

### VLAN スパンニングの仕組み
{: #how-vlan-spanning-works}

VLAN スパンニングを有効にすると、ルーティングされるすべてのトラフィックが、アカウント上のすべてのプライベート VLAN をまたいですべてのプライベート・サブネット間を行き来できるようになります。これにより、ルーティングされるトラフィックのグローバルな通信が必要となるビジネス・ニーズに対応できます。例えば、同じ VLAN または異なる VLAN の複数のプライベート・サブネット間でデバイスの通信が必要な場合などに、VLAN スパンニングを有効にします。

スパンニングを有効にすると、アカウント全体に影響します。VLAN スパンニングから特定のサブネット、VLAN、またはデバイスを除外することはできません。プライベート・サブネットだけを使用してサーバーを役割や階層ごとに分離している場合は、VLAN スパンニングを有効すると、その分離がなくなってしまいます。
{:note}

### デフォルト値
{: #vlan-spanning-default-values}

デフォルトでは、VLAN スパンニングは無効です。2 つの異なるプライベート・サブネット上のデバイスは、VLAN が同じであろうと異なっていようと、IP トラフィックを相互に送信することはできません。

### VLAN スパンニングを必要とすることが多いサービス
{: #vlan-spanning-services}

状況に応じて VLAN スパンニングをセットアップできるように、詳しいチュートリアルが用意されています。[他のリソース](/docs/infrastructure/vlans?topic=vlans-other-resources-for-vlan-spanning)へのリンクを参照してください。


## VLAN スパンニングの管理
{: #manage-vlan-spanning}

アカウントの VLAN スパンニングを有効または無効にできます。
{: shortdesc}

アカウント設定を更新するには、次の手順に従います。

  1. ブラウザーから、[{{site.data.keyword.Bluemix_notm}} コンソール ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://{DomainName}/){: new_window} を開き、アカウントにログインします。
  2. メニューで、**「インフラストラクチャー」**を選択します。 カスタマー・ポータルが開きます。
  3. カスタマー・ポータルのナビゲーションで、**「ネットワーク」>「IP 管理」>「VLAN」**を選択します。
  4. **「スパン」**タブを選択して、VLAN スパンニング・セクションにアクセスします。
  5. **「オン」**または**「オフ」**ラジオ・ボタンを選択し、VLAN スパンニングを有効または無効にします。

短時間で VLAN スパンニングを切り替えると、アプリケーションで遅延が生じることがあります。
{:note}

更新要求は、最大で処理に 15 分かかることがあります。画面に変更の確認が表示されます。前述の手順を繰り返して、何度でも VLAN スパンニングの設定を更新できます。

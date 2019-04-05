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

# FAQ
{:#vlans-faqs}


## 既存のデバイスを新しい VLAN に移動できますか?
{: faq}

既存のデバイスは他の VLAN に移動できます。ただし、移動が要求された場合に限られます。 VLAN はルーターに関連付けられており、各ルーターへの接続はデバイスの物理的なロケーションに基づいているため、一部の VLAN の移動には、物理的な再配置も必要になることがあります。 このことは、新しい VLAN を別のデータ・センターに配置する場合には常に当てはまりますが、デバイスを同一データ・センター内の別の VLAN へ移動するときにも該当する場合があります。 このような変更を行うと、接続が新しい VLAN へ移動されるとき、ネットワーク接続が中断され、デバイスの IP アドレスの変更が必要になります。 移動期間中はマシンがオフラインになるため、デバイスを新しい VLAN に移動するときは、ゆとりを持った計画をお願いします。


## 注文時にデバイスで使用する VLAN を指定する手段はありますか?
{: faq}

はい。注文プロセスで特定の VLAN を選択できます。デバイスを注文するとき、注文フォームの最後にこのオプションが表示されます。 プライベート VLAN が選択済みの状態で、その後にパブリック VLAN があります。 また、VLAN ごとにサブネットを選択するセレクターも表示されることに注意してください。この選択は**オプション**です。選択すべき理由がある場合にのみサブネットを選択してください。利用できる IP アドレスが少ないサブネットを選択すると、デバイスの設置に悪影響があります (詳しくは、[サブネット FAQ](/docs/infrastructure/subnets?topic=subnets-subnets-faq) を参照してください)。

選択する VLAN は、デバイスと同じデータ・センター内に存在するものでなければならないことに注意してください。異なるデータ・センター内にある VLAN にデバイスを割り当てることはできません。


## 単一の VLAN にいくつのデバイスを割り当てられますか?
{: faq}

現時点では、単一の VLAN に関連付けられるデバイスの数に制限はありません。ただし、ハードウェア・ファイアウォールを VLAN に関連付けた場合は、ファイアウォールの種類によっては、VLAN 上に置けるデバイスの数に制限がかかる
ことがあります。


## どのような種類のデバイスが VLAN に割り当てられますか?
{: faq}

ネットワーク接続を使用できるあらゆるデバイスが VLAN に関連付けられます。 専用サーバーはパブリック・ネットワークにもプライベート・ネットワークにも接続するので、専用サーバーのデバイスには、パブリック VLAN とプライベート VLAN の両方が関連付けられます。

## サーバーに VLAN をトランク接続するにはどうしたらよいですか?
{: faq}

VLAN をベアメタル・サーバーにトランク接続するには API を使用するしかありません。ポータル・インターフェースでは、この操作はできません。
トランクの VLAN を管理する方法について詳しくは、以下の API 資料リンクを参照してください。
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## VLAN を注文しようとすると、使用可能な VLAN がないと表示されるのですが、どういう意味でしょうか?
{: faq}

[容量に関する注意事項](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity)を参照してください。


## 同じプライベート VLAN 上にあるデバイス間で相互通信できないのはなぜですか?
{: faq}

サブネットが異なるサーバーどうしは、デフォルトでは、IP アドレスを介して通信することができません。原則としては、同じ VLAN (第 2 層構造) 上にあるサーバーは、OSI モデルの第 2 層の方式で通信できます。インターネット・プロトコル (IP) (第 3 層) 通信を有効にするには、通信したいサブネットへの経路を各サーバーに追加する (経路はサーバーによって異なります) か、[VLAN スパンニング](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)を有効にします。[VLAN スパンニング](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)はさまざまな影響を与えるため、有効にする前に機能の詳細を確認してください。


## 同一 VLAN 内のプライベート・サブネット間のデバイス通信がデフォルトで必要だけれども、VLAN スパンニングは有効にしたくないという場合、他にどのような方法がありますか?
{: faq}

{{site.data.keyword.cloud}} がプライマリー・サブネットを必要に応じて自動的に割り当て/削除することを考えると、サーバー上の経路を管理するのが煩雑な作業になることは目に見えています。また、[VLAN スパンニング](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)は常に適用可能というわけではありません。こうした性質が大規模デプロイメントを阻む要素になっている場合は、プライマリー・サブネットを
[プレミアム VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans) からのみ割り当てるように要求すると良いでしょう。そのサブネットは課金対象になります。料金は要求ごとに異なります。このような要求を認めるかお断りするかは、IBM がその都度 (アカウント単位ではなく要求ごとに) 判断します。特別なサイズのプライマリー・サブネットを要求するには、以下の手順に従ってください。

  1. [IBM Cloud コンソール ![外部リンク・アイコン](../../icons/launch-glyph.svg "外部リンク・アイコン")](https://{DomainName}/){: new_window} を開き、アカウントにログインします。
  1. メニューで、**「クラシック・インフラストラクチャー」**を選択します。 
  1. クラシック・インフラストラクチャーのナビゲーション・メニューで、**「ネットワーク」>「IP 管理」>「VLAN」**を選択します。
  1. 必要に応じてプレミアム VLAN を注文します。[プレミアム VLAN の注文](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans)を参照してください。
  1. メニューの**「サポート」>「チケットの追加」**に移動してチケットを開きます。
    - 件名: 「プライベート・ネットワークの質問 (Private Network Question)」または「パブリック・ネットワークの質問 (Public Network Question)」
    - タイトル: 「ラージ・プライマリー・サブネットの要求 (Large Primary Subnet Request)」
    - 詳細: datacenter.router.vlan 表記 (例: ams03.bcr01.1234) を使用してサブネットを必要とするプレミアム VLAN を指定してください。次に、希望するサブネットのサイズを CIDR 表記 (例: /25) で指定してください。購入する予定のサーバー数とその期間を記入します。また、要求するサブネットがないと、どのような支障をきたすのかも説明します。支障が生じる状況について詳しく記述してください。そのような意見が IBM のプラットフォームの改善方法を検討するときに役に立つからです。サブネットの他のプロパティーが考慮されることはないので、これ以上記入する必要はありません。

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

# VLAN について
{:#about-vlans}

VLAN は、リソースにトラフィックを送信するうえで中心的な役割を果たすものです。VLAN は自動的に管理されるため、ユーザーが直接 VLAN を操作する必要はありません。必要になったら割り当てられ、不要になったら削除されます。

VLAN は一種のネットワーク概念です。VLAN は、[OSI モデル ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://en.wikipedia.org/wiki/OSI_model) の第 2 層、_データ・リンク層_にブロードキャスト・ドメインを作成することを可能にします。VLAN はパケットを識別するための特定の手段を提供することで、複数のワークロードを同じ物理装置上に
共存させます。VLAN について詳しくは、[こちらの記事 ![外部リンクのアイコン](../../icons/launch-glyph.svg "外部リンクのアイコン")](https://en.wikipedia.org/wiki/Virtual_LAN) を参照してください。

## VLAN の種類
{:#types-of-vlans}

{{site.data.keyword.cloud}} には、**自動** VLAN と**プレミアム** VLAN という 2 種類の VLAN があります。種類ごとに役割が異なるので、要件に合わせられるように、違いについて理解しておくことが重要です。

### 自動 VLAN
{:#automatic-vlans}

自動 VLAN は、{{site.data.keyword.cloud}} で自動的に管理される VLAN です。お客様から注文された他の製品の要件を満たす目的で、必要に応じて割り当てられ、削除されます。通常は、ルーターごとに自動 VLAN が 1 つ用意されます。特定の VLAN を選択しなくても、注文したサーバーには自動 VLAN が関連付けられます。自動 VLAN の注文やキャンセルはできません。自動 VLAN は IBM システムが必要だと判断した場合にのみアカウントに提供され、IBM システムが不要になったと判断した場合には削除されるものであるからです。

### プレミアム VLAN
{:#about-premium-vlans}

プレミアム VLAN は、VLAN を注文することで割り当てられます。手順については、[プレミアム VLAN の注文](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans)を参照してください。プレミアム VLAN は、明示的にキャンセルするまでアカウントに存在します。プレミアム VLAN は、容量制限の範囲内でいくつでも注文できます。容量制限に達した場合は、別のポッドまたはデータ・センターで VLAN を注文してください。

プレミアム VLAN の重要な性質は、サーバーの注文を満たす目的で自動的に選択されるものではないという点です。プレミアム VLAN 上にサーバーを配置するためには、サーバーを注文するプロセスの中で、プレミアム VLAN を明示的に選択する必要があります。VLAN 選択に関する手順については、[FAQ](/docs/infrastructure/vlans?topic=vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-) を参照してください。


## VLAN ID
{:#vlan-identification}

VLAN は、IBM Cloud データ・センター内のルーター上に存在します。各 VLAN は、固有の番号、ルーター、およびデータ・センター・ロケーションの組み合わせによって識別されます。例えば、データ・センター `SJC01` 内のルーター `fcr02` 上にあるパブリック `VLAN 829` は、`sjc01.fcr02.829` として識別されます。データ・センター `AMS01` 内のルーター `bcr01` 上にあるプライベート VLAN 2234 は、`ams01.bcr01.2234` として識別されます。


## VLAN とサブネット
{:#vlans-subnets}

VLAN にはサブネットを 1 つ以上含めることができます。VLAN と同様に、一部のサブネットは、デバイスの IP アドレスの必要性に応じて自動的に追加/削除されます。存在し得るサブネットおよびその機能について詳しくは、[サブネットと IP](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips) を参照してください。


## VLAN 内の通信
{:#communication-within-vlans}

1 つの VLAN 上に存在するすべてのリソースが通信できます。ただし、デフォルトでできるわけではありません。VLAN は OSI モデルの第 2 層構造であり、サブネット/IP は第 3 層構造であることを忘れないでください。層ごとに別の方法で通信が行われます。ネットワークがパブリックかプライベートかによらず、別々の VLAN 上に存在するリソースが、第 2 層の方式で相互通信することはできません。

### パブリック・ネットワーク上の VLAN 内の通信
{:#communication-within-vlans-public}

パブリック・ネットワーク上のリソース間の通信にかかる固有の制約はありません。リソースが存在する VLAN の 1 つ以上が {{site.data.keyword.cloud}} のパブリック・ネットワーク・インフラストラクチャー内のものであろうとインターネット内のものであろうと関係ありません。ファイアウォールやゲートウェイ・アプライアンスを導入すれば、制約を追加できます。

### プライベート・ネットワーク上の 1 つの VLAN 内の通信
{:#communication-within-vlans-private}

デフォルトでは、同じ VLAN に複数のサブネットが存在していても、通信できるのは同一サブネット内のコンピュートだけです。ただし、コンピュート・インスタンスが同じ VLAN 上の他のサブネットへの経路エントリーを持っている場合は、
同一 VLAN 上の他のサブネットと通信できます。プライベート・サブネット間通信を必要とするすべてのコンピュート・ノードの経路エントリーを管理する作業は、非常に煩雑な作業になる可能性があります。同じ VLAN 内のすべてのコンピュート間でデフォルトで通信できなければならない場合は、[VLAN スパンニング](/docs/infrastructure/vlans?topic=vlans-vlan-spanning)を参照してください。VLAN スパンニングが及ぼす影響は大きいため、有効にする前に慎重に検討してください。

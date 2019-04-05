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

# Einführung in VLANs
{:#getting-started-with-vlans}

Virtual Local Area Networks (VLANs) werden von {{site.data.keyword.cloud}} verwendet, um den Broadcast-Datenverkehr in öffentlichen und privaten Netzen zu isolieren. VLANs werden nach Bedarf zugeordnet, um die Anforderungen anderer Angebote zu erfüllen. Wenn Sie beispielsweise Rechenleistung in einem Rechenzentrum bestellen, in dem Sie noch nicht präsent sind, erhalten Sie automatisch ein VLAN. Weitere Bestellungen von Rechenleistung in demselben Rechenzentrum, für die keine Netzanforderungen angegeben sind, werden in der Regel in das vorher zugewiesene VLAN platziert. Alle VLANs, die automatisch zugeordnet werden, werden auch wieder automatisch entfernt, wenn sie für die Ressourcen nicht mehr erforderlich sind.

VLANs sind für Router vorgesehen, die in IBM Cloud-Rechenzentren verwendet werden; in einem Rechenzentrum sind mehrere Router sowohl für öffentliche als auch private Netze vorhanden. So ist es möglich, dass in einem einzigen Rechenzentrum mehrere VLANs zugeordnet werden können. Es ist auch möglich, zusätzliche VLANs zu bestellen, um komplexere Netztopologien zu erstellen, in der Regel in Verbindung mit einer [Virtual Router Appliance](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance).

Gekaufte VLANs werden als **Premium-VLANs** und automatisch von {{site.data.keyword.cloud}} verwaltete VLANs als **Automatische VLANs** bezeichnet. Weitere Information zur Funktionsweise von VLANs finden Sie im Abschnitt [Informationen zu VLANs](/docs/infrastructure/vlans?topic=vlans-about-vlans).


## VLANs verwalten
{:#managing-vlans}

Führen Sie die folgenden Schritte aus, um die VLANs auf Ihrem Konto zu überprüfen.

  1. Öffnen Sie die [IBM Cloud-Konsole ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/){: new_window} und melden Sie sich bei Ihrem Konto an.
  2. Wählen Sie **Infrastruktur** im Menü aus.
  3. Wählen Sie über die Navigation des Kundenportals die Optionen **Netz > IP-Verwaltung > VLANs** aus.

In der Liste der VLANs werden Informationen zu den VLANs angezeigt und die Anzeige bietet Zugriff auf jedes VLAN und die zugeordneten Einheiten oder Teilnetze. 

### Erläuterungen zur Auswahl eines Pods im Gegensatz zur Auswahl eines Rechenzentrums
{:#pod-vs-datacenter-selection}

Die Optionen für die Bestellung eines VLANs orientieren sich an den unterschiedlichen Anforderungen und Einschränkungen. In diesem Abschnitt werden die Gründe zusammengefasst, die dazu führen können, dass eine Option einer anderen vorgezogen wird.

Mit der Option **Nach Pod bestellen** können Sie den genauen Pod (und somit den Router) angeben, für den Sie ein VLAN benötigen. Verwenden Sie diese Option, wenn Sie einen konkreten Grund dafür haben, das VLAN für diesen Pod zu verwenden. Zu den Gründen für die Auswahl dieser Option gehören die Verwendung des VLANs mit einer vorhandenen Gateway-Appliance oder einer Firewall für mehrere VLANs. Wenn Sie zusätzliche VLANs als Teil eines größeren Bereitstellungsschemas bestellen, wissen Sie normalerweise, in welchem Pod die VLANs enthalten sein sollen. Ist dies der Fall, wählen Sie diese Option aus.

Verwenden Sie die Option **Nach Rechenzentrum bestellen**, wenn der Standort des VLANs weniger wichtig ist. Diese Option eignet sich am besten, wenn Sie einen Standort einrichten möchten, für den das Clustering weiterer Ressourcen geplant ist. Wenn für Ihre Bereitstellungen das Netz an erster Stelle steht (und nicht das Bestellen der Server), ist die Verwendung dieser Option für den Aufbau einer Präsenz in einem neuen Rechenzentrum die beste Wahl. Die Anforderungen der VLANs werden von einem beliebigen Pod im ausgewählten Rechenzentrum erfüllt; welcher Pod verwendet wird, kann bei Auswahl dieser Option nicht vorhergesagt werden.

Es ist am besten, die am wenigsten konkrete verfügbare Standortoption zu verwenden, die Ihren Anforderungen entspricht.

### Komplexe Bestellungen
{:#complex-orders-vlans}

Bei der Bestellung im Portal kann pro Bestellung nur eine einzige VLAN-Konfiguration bestellt werden. Eine Konfiguration besteht aus dem gewünschten Netz, der gewünschten Standortoption und der gewünschten Menge. Zwar können über die API in einer einzigen Bestellung mehrere VLAN-Konfigurationen bestellt werden, die Menge für jede einzelne Konfiguration ist jedoch auf 1 begrenzt; dies bedeutet, dass jede angegebene VLAN-Konfiguration unabhängig von den anderen realisiert wird. Wenn also für jede Konfiguration die Option für den Rechenzentrumsstandort verwendet wird, kann jedes VLAN anderen Pods in diesem Rechenzentrum zugeordnet werden.

### Anmerkung zur Kapazität
{:#note-about-capacity}

Es kann vorkommen, dass der Versuch, ein VLAN zu bestellen, aufgrund von Kapazitätseinschränkungen am ausgewählten Standort verhindert wird. Falls dies der Fall ist, wirkt sich dies auf alle Benutzer aus, die versuchen, VLANs an diesem Standort zu bestellen; es bestehen keine Regressansprüche. Es wird empfohlen, soweit möglich eine Präsenz in einem weiteren Rechenzentrum aufzubauen und die Vorzüge des [VLAN-Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) in Erwägung zu ziehen. Wenn Sie bei der Wahl des Standorts flexibel sind, ist es am besten, bei der Bestellung der VLANs die am wenigsten konkrete Standortoption zu verwenden, da so eine größere Flexibilität bei der Zuordnung der VLANs möglich ist. Außerdem kann die VLAN-Kapazität an dem vorher versuchten Standort zu einem späteren Zeitpunkt wieder verfügbar werden.


## Premium-VLANs stornieren
{:#canceling-premium-vlans}

Wenn Sie ein Premium-VLAN entfernen möchten, suchen Sie dieses VLAN in der VLAN-Liste Ihres Kontos (siehe unter 'VLANs verwalten') und klicken Sie auf das Symbol 'X' in dem Eintrag, um die Eingabeaufforderung für die Stornierung aufzurufen.

Premium-VLANs können nicht storniert werden, wenn sie von anderen Produkten verwendet werden. Bei den folgenden Verwendungen ist eine Stornierung nicht möglich:

  * Server, die sich direkt im VLAN befinden (im Gegensatz zu Servern, die per Trunking verbunden sind).
  * Sekundäre Teilnetze, die an das VLAN oder eine IP-Adresse im VLAN weitergeleitet werden.
  * Firewall-Produkte, die im gesamten VLAN bereitgestellt werden. Davon ausgeschlossen sind zum Beispiel nicht dedizierte Hardware-Firewalls.
  * Zuordnung zu einer Gruppe für automatische Skalierung.
  * Trunking-Funktion zu Servern (dies wird sich in der Zukunft ändern).

Zudem wird durch manche Produkte und Komponenten die **Stornierung eines VLAN nicht verhindert**, sie werden jedoch durch die Entfernung beeinträchtigt. Zu ihnen gehören:

  * Alle, die durch eine Virtual Router Appliance geschützt werden. Die VLAN-Zuordnung wird unabhängig von einer Umgehung entfernt.

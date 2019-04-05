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

# Häufig gestellte Fragen (FAQs)
{:#vlans-faqs}


## Kann ich eine vorhandene Einheit in ein neues VLAN verschieben?
{: faq}

Vorhandene Einheiten können nur dann in andere VLANs verschoben werden, wenn das Verschieben angefordert wird. Da VLANs an einen Router gebunden sind und die Verbindungen zu jedem Router vom physischen Standort der Einheit abhängig sind, erfordern manche VLAN-Verschiebungen auch eine physische Standortänderung. Dies ist stets der Fall, wenn sich das neue VLAN in einem anderen Rechenzentrum befindet, es kann jedoch auch beim Verschieben einer Einheit in ein anderes VLAN innerhalb desselben Rechenzentrums vorkommen. Durch das Ausführen dieser Änderung wird die Netzkonnektivität unterbrochen und es ist eine Änderung der IP-Adresse der Einheit erforderlich, wenn die Verbindung zum neuen VLAN verschoben wird. Wenn eine Einheit in ein neues VLAN verschoben werden soll, muss für eine umfassende Planung gesorgt werden, da die betreffende Maschine für die Dauer des Verschiebens offline sein wird.


## Kann ich beim Bestellen angeben, welches VLAN ich für meine Einheit verwenden möchte?
{: faq}

Ja, während des Bestellablaufs kann ein bestimmtes VLAN ausgewählt werden. Beim Bestellen einer Einheit ist diese Option am Ende des Bestellformulars verfügbar. Zunächst ist ein privates VLAN und anschließend ein öffentliches VLAN ausgewählt. Beachten Sie außerdem, dass für jedes VLAN ein Teilnetzselektor angezeigt wird; diese Auswahl ist **optional**. Wählen Sie nur ein Teilnetz aus, wenn Sie einen Grund dafür haben; wenn Sie ein Teilnetz auswählen, in dem verfügbare IP-Adressen fehlen, wirkt sich dies negativ auf die Auftragserfüllung des Geräts aus (weitere Informationen hierzu finden Sie unter [Häufig gestellte Fragen zu Teilnetzen](/docs/infrastructure/subnets?topic=subnets-subnets-faq)).

Es ist wichtig zu beachten, dass sich das ausgewählte VLAN in demselben Rechenzentrum wie die Einheit befinden muss. Eine Einheit kann nicht einem VLAN zugeordnet werden, das sich in einem anderen Rechenzentrum befindet.


## Wie viele Einheiten können einem einzelnen VLAN zugeordnet werden?
{: faq}

Derzeit besteht keine Begrenzung bezüglich der Anzahl der Einheiten, die zu beliebiger Zeit einem einzelnen VLAN zugeordnet sind; wenn einem VLAN jedoch eine Hardware-Firewall zugeordnet ist, geben die Regeln für die Firewall möglicherweise Beschränkungen in Bezug auf die Anzahl der Einheiten vor, die sich im VLAN befinden.


## Welche Arten von Einheiten werden einem VLAN zugeordnet?
{: faq}

Jede Einheit, die über eine Netzverbindung verfügt, wird einem VLAN zugeordnet. Dedizierte Server verfügen über eine öffentliche und eine private Netzverbindung, daher werden diese Einheiten öffentlichen und privaten VLANs zugeordnet.

## Wie verwende ich die Trunking-Funktionalität für Verbindungen von VLANs zu Servern?
{: faq}

Die Trunking-Funktionalität zwischen VLANs und Bare-Metal-Servern kann nur über die API verwendet werden; für diese Aktivität ist keine Portalschnittstelle verfügbar. Weitere Informationen zum Verwalten von VLANs als Trunks finden Sie in den unten aufgeführten Links zur API-Dokumentation.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## Was bedeutet beim Bestellen eines VLANs der Hinweis, dass keine VLANs verfügbar sind?
{: faq}

Informationen hierzu finden Sie unter [Anmerkung zur Kapazität](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity).


## Warum können meine Geräte in demselben privaten VLAN nicht miteinander kommunizieren?
{: faq}

Wenn sich jeder Server in einem anderen Teilnetz befindet, können sie standardmäßig nicht über IP-Adressen miteinander kommunizieren. Technisch gesehen können Ihre Server mit den Methoden der OSI-Modellschicht 2 kommunizieren, da sie sich in demselben VLAN befinden (ein Konstrukt von Schicht 2). Damit die Kommunikation über das Internetprotokoll (auch als Schicht 3 bezeichnet) funktioniert, können Sie eine Route für das Teilnetz hinzufügen, mit dem Sie auf jedem einzelnen Server kommunizieren möchten (die Route ist auf jedem einzelnen Server unterschiedlich), oder Sie können die Option [VLAN-Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) aktivieren. Beachten Sie, dass das [VLAN-Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) zusätzliche Auswirkungen aufweist; überprüfen Sie die Funktion daher ausführlich, bevor Sie sich für ihre Aktivierung entscheiden.


## Welche Optionen habe ich, wenn Einheiten in verschiedenen privaten Teilnetzen in demselben VLAN standardmäßig miteinander kommunizieren sollen, ich aber nicht das VLAN-Spanning aktivieren möchte?
{: faq}

Angesichts der Tatsache, dass primäre Teilnetze von {{site.data.keyword.cloud}} je nach Bedarf automatisch zugeordnet werden, ist die Verwaltung von Routen auf Servern umständlich. Auch die Verwendung des [VLAN-Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) ist nicht immer möglich. Wenn Sie über eine große Bereitstellung verfügen, die durch dieses Verhalten behindert wird, können Sie nur ein primäres Teilnetz in einem [Premium-VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans) anfordern, das angepasst werden kann. Die Gebühren werden für dieses Teilnetz abgerechnet und können abhängig von der Anforderung variieren. Es liegt in Ihrem Ermessen, solche Anforderungen von Fall zu Fall zu akzeptieren oder abzulehnen (nicht Konto für Konto, sondern für jede einzelne Anforderung). Gehen Sie gemäß den folgenden Anweisungen vor, um ein primäres Teilnetz mit einer bestimmten Größenangabe anzufordern:

  1. Öffnen Sie die [IBM Cloud-Konsole ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/){: new_window} und melden Sie sich bei Ihrem Konto an.
  1. Wählen Sie im Menü **Klassische Infrastruktur** aus.  
  1. Wählen Sie im Navigationsmenü 'Klassische Infrastruktur' **Netz > IP-Verwaltung > VLANs** aus.
  1. Bestellen Sie bei Bedarf ein Premium-VLAN. Informationen hierzu finden Sie im Abschnitt [Premium-VLANs bestellen](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans).
  1. Öffnen Sie durch das Navigieren zu **Unterstützung > Ticket hinzufügen** im Menü ein Ticket.
    - Betreff: 'Private Network Question' (Frage zu privaten Netzen) oder 'Public Network Question' (Frage zu öffentlichen Netzen)
    - Titel: 'Large Primary Subnet Request' (Anforderung für großes primäres Teilnetz)
    - Details: Geben Sie mithilfe der Notation 'rechenzentrum.router.vlan' (zum Beispiel ams03.bcr01.1234) das Premium-VLAN an, in dem das Teilnetz verwendet werden soll. Geben Sie danach die gewünschte Teilnetzgröße in einer CIRD-Notation an (zum Beispiel /25). Geben Sie die Anzahl der Server und den Zeitraum für den Kauf an. Erläutern Sie auch, wie die Verwendung ohne das angeforderte Teilnetz behindert wird. Erklären Sie ausführlich die Behinderungen in Ihrer Situation, da dies bei der Beurteilung der Verbesserungen für Ihre Plattform  hilfreich ist. Da keine weiteren Eigenschaften des Teilnetzes berücksichtigt werden, sind weitere Angaben nicht erforderlich.

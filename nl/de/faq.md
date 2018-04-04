---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-17"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Häufig gestellte Fragen (FAQs)


## Kann ich eine vorhandene Einheit in ein neues VLAN verschieben?

Vorhandene Einheiten können nur dann in andere VLANs verschoben werden, wenn das Verschieben angefordert wird. Da VLANs an einen Router gebunden sind und die Verbindungen zu jedem Router vom physischen Standort der Einheit abhängig sind, erfordern manche VLAN-Verschiebungen auch eine physische Standortänderung. Dies ist stets der Fall, wenn sich das neue VLAN in einem anderen Rechenzentrum befindet, es kann jedoch auch beim Verschieben einer Einheit in ein anderes VLAN innerhalb desselben Rechenzentrums vorkommen. Durch das Ausführen dieser Änderung wird die Netzkonnektivität unterbrochen und es ist eine Änderung der IP-Adresse der Einheit erforderlich, wenn die Verbindung zum neuen VLAN verschoben wird. Wenn eine Einheit in ein neues VLAN verschoben werden soll, muss für eine umfassende Planung gesorgt werden, da die betreffende Maschine für die Dauer des Verschiebens offline sein wird.


## Kann ich beim Bestellen angeben, welches VLAN ich für meine Einheit verwenden möchte?

Ja, während des Bestellablaufs kann ein bestimmtes VLAN angegeben werden. Beim Bestellen einer Einheit ist diese Option am Ende des Bestellformulars verfügbar. Zunächst ist ein privates VLAN und anschließend ein öffentliches VLAN ausgewählt. Es ist wichtig zu beachten, dass sich das VLAN im selben Rechenzentrum wie die Einheit befinden muss. Eine Einheit kann nicht einem VLAN zugeordnet werden, das sich in einem anderen Rechenzentrum befindet.

## Wie viele Einheiten können einem einzelnen VLAN zugeordnet werden?

Derzeit besteht keine Begrenzung bezüglich der Anzahl der Einheiten, die zu beliebiger Zeit einem einzelnen VLAN zugeordnet sind. Wenn einem VLAN jedoch eine Hardware-Firewall zugeordnet ist, geben die Firewallregeln möglicherweise Beschränkungen vor in Bezug auf die Anzahl der Einheiten, die sich im VLAN befinden.

## Funktionieren VLANs sowohl im öffentlichen als auch im privaten Netz?

Ja, es gibt sowohl öffentliche als auch private VLANs. In den meisten Fällen verfügt eine Einheit sowohl über eine öffentliche als auch eine private Verbindung. Das bedeutet, die Einheit verfügt sowohl in einem öffentlichen als auch in einem privaten VLAN über eine Verbindung.

## Welche Arten von Einheiten werden einem VLAN zugeordnet?

Jede Einheit, die über eine Netzverbindung verfügt, wird einem VLAN zugeordnet. Dedizierte Server verfügen über eine öffentliche und eine private Netzverbindung, daher werden diese Einheiten öffentlichen und privaten VLANs (ein VLAN pro Verbindungstyp und pro Einheit) zugeordnet.

Für Hardware-Firewalls gelten andere Bedingungen: Sie werden vor einem VLAN positioniert, um Datenverkehr abzufangen und zu filtern. Diese Einheiten werden an das VLAN gebunden, das sie bedienen, aber sie befinden sich nicht tatsächlich im VLAN selbst.

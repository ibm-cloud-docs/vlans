---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-20"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Einführung in VLANs

Ein VLAN ist ein virtuelles LAN (Local Area Network), das erstellt werden kann, um es Kunden zu ermöglichen, Teile eines größeren Netzes in kleinere Teilnetze aufzutrennen. Ein VLAN dient als Container, in dem Verbindungen und IP-Adressen eines einzelnen Kunden separat von denen aller anderen Kunden aufbewahrt werden können. VLANs ermöglichen eine höhere Sicherheit und die Isolation bestimmter Themenbereiche. Im {{site.data.keyword.BluSoftlayer_notm}}-Netz bieten VLANs Ihnen die Möglichkeit, Ihre Einheiten und Teilnetze zu partitionieren. 

Sie können Ihre VLANs über die Anzeige für VLANs verwalten, indem Sie folgende Schritte ausführen:

1. Öffnen Sie über Ihren Browser das [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){: new_window} und melden Sie sich an Ihrem Konto an.
2. Wählen Sie über die Navigation des Kundenportals die Optionen **Netz > IP-Verwaltung > VLANs** aus.

In der Anzeige für VLANs werden Informationen zu Ihren VLANs angezeigt und die Anzeige bietet Zugriff auf jedes VLAN und die zugeordneten Einheiten oder Teilnetze. Als zusätzlichen Service können Kunden das VLAN-Spanning aktivieren, bei dem alle privaten Netz-VLANs für ein Konto verbunden werden. Auf diese Weise wird Einheiten auf separaten VLANs die Kommunikation miteinander ermöglicht. 

## VLAN-Identifikation

VLANs befinden sich auf Routern innerhalb unserer Rechenzentren. Jedes VLAN wird durch eine eindeutige Nummer, einen eindeutigen Router und einen eindeutigen Rechenzentrumsstandort identifiziert. Beispiel: `VLAN 829`, das sich auf dem Router `fcr02` im Rechenzentrum `SJC01` befindet, wird von unseren Systemen als `829 fcr02.sjc01` identifiziert.

## VLAN-Spanning

VLAN-Spanning ist eine Kontoeinstellung, bei der Datenverkehr möglich ist zwischen privaten VLANs, die zu einem einzigen Konto gehören. Aufgrund der Art des privaten Netzes wird nur eine sehr geringe Menge an Datenverkehr in die privaten VLANs eines Kontos zugelassen. Im Allgemeinen schützen VLANs Einheiten vor Netzverkehr auf anderen Kundenkonten. Bei privaten VLANs reicht dieser Schutz einen Schritt weiter, indem der Datenverkehr im VLAN beschränkt wird und ausschließlich zwischen den Einheiten in diesem VLAN erfolgt. Einheiten, die sich auf zwei unterschiedlichen privaten VLANs befinden, können standardmäßig daher keine Daten untereinander senden. Durch das [Aktivieren von VLAN-Spanning](vlan-spanning.html) wird diese Einschränkung aufgehoben, sodass Einheiten in den verschiedenen privaten VLANs eines Kontos miteinander kommunizieren können.

### Wann sollte ich VLAN-Spanning für mein Konto aktivieren?

VLAN-Spanning sollte aktiviert werden, wenn eine entsprechende Geschäftsanforderung gegeben ist. Wenn beispielsweise Server, die sich auf mehreren privaten Teilnetzen befinden, miteinander kommunizieren müssen, sollte VLAN-Spanning aktiviert werden. Die Kommunikation zwischen VLANs ist nicht spezifisch für den physischen Standort des VLAN. Private VLANs im selben Rechenzentrum sind beispielsweise dennoch vollkommen getrennt voneinander. Wenn Einheiten mit jeweils eigenem Teilnetz sich in zwei oder mehr VLANs befinden, muss VLAN-Spanning aktiviert werden, damit die Einheiten miteinander kommunizieren können.

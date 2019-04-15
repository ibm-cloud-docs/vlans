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

# Informationen zu VLANs
{:#about-vlans}

VLANs sind ein wesentliches Element beim Steuern des Datenverkehrs zu den Ressourcen. Sie brauchen wahrscheinlich nie direkt mit VLANs interagieren, da diese automatisch verwaltet werden: Sie werden nach Bedarf zugeordnet und entfernt.

Ein VLAN ist ein Netzkonzept. Es ermöglicht das Erstellen von Broadcastdomänen auf Schicht 2 des [OSI-Modells ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://en.wikipedia.org/wiki/OSI_model), der _Datenverbindungsschicht_. Von VLANs wird eine Methode zur Paketerkennung bereitgestellt und das Koexistieren mehrerer Workloads auf denselben physischen Geräten ermöglicht. Weitere Informationen zu VLANs finden Sie unter [Virtual LAN ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://en.wikipedia.org/wiki/Virtual_LAN).

## VLAN-Typen
{:#types-of-vlans}

Es gibt zwei verschiedene VLAN-Typen, die in {{site.data.keyword.cloud}} als **Automatisch** und **Premium** bezeichnet werden. Da beide bestimmte Eigenschaften aufweisen, ist es wichtig, sich mit diesen Unterschieden vertraut zu machen, um sie abhängig von den jeweiligen Anforderungen verwenden zu können. 

### Automatische VLANs
{:#automatic-vlans}

Automatische VLANs werden von {{site.data.keyword.cloud}} automatisch verwaltet; sie werden zugeordnet und entfernt, um die Anforderungen anderer Produkte zu erfüllen, die Sie bestellen. In der Regel verfügen Sie über ein automatisches VLAN pro Router. Automatische VLANs werden Servern zugeordnet, die ohne Auswahl eines bestimmten VLANs bestellt wurden. Es ist nicht möglich, automatische VLANs zu bestellen oder zu stornieren, da sie nur im Konto vorhanden sind, wenn von Systemen von IBM ermittelt wird, dass sie erforderlich sind; sie werden entfernt, wenn diese Systeme feststellen, dass sie nicht mehr benötigt werden.

### Premium-VLANs
{:#about-premium-vlans}

Premium-VLANs werden durch die Bestellung eines VLANs erworben. Anweisungen hierzu finden Sie im Abschnitt [Premium-VLANs bestellen](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans). Premium-VLANs bleiben in Ihrem Konto, bis sie explizit storniert werden. Abgesehen von Kapazitätsbeschränkungen können Sie so viele Premium-VLANs bestellen, wie Sie möchten. Falls nicht ausreichend Kapazität vorhanden ist, suchen Sie VLANs in einem anderen Pod oder Rechenzentrum.

Ein wichtiger Unterschied zwischen Premium-VLANs und automatischen VLANs besteht darin, dass Premium-VLANs nicht automatisch ausgewählt werden, damit eine Serverbestellung erfüllt wird. Premium-VLANs müssen während des Bestellablaufs für einen Server explizit ausgewählt werden, damit die Server verwendet werden. Anweisungen zur VLAN-Auswahl finden Sie im Abschnitt [Häufig gestellte Fragen](/docs/infrastructure/vlans?topic=vlans-vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-).


## VLAN-Identifikation
{:#vlan-identification}

VLANs befinden sich auf Routern in IBM Cloud-Rechenzentren. Jedes VLAN wird durch eine eindeutige Kombination aus einer Nummer, dem Router und dem Rechenzentrumsstandort angegeben. Beispiel: Das öffentliche `VLAN 829`, das sich auf dem Router `fcr02` im Rechenzentrum `SJC01` befindet, wird als `sjc01.fcr02.829` angegeben. Das private VLAN 2234, das sich auf Router `bcr01` in Rechenzentrum `AMS01` befindet, wird als `ams01.bcr01.2234` angegeben.


## VLANs und Teilnetze
{:#vlans-subnets}

VLANs können mindestens ein Teilnetz enthalten. Wie VLANs werden manche Teilnetze automatisch hinzugefügt und entfernt, falls für Geräte IP-Adressen erforderlich sind. Informationen zu den möglichen vorhanden Teilnetzen und ihrer Funktionsweise finden Sie im Abschnitt [Teilnetze und IPs](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips).


## Kommunikation in einem VLAN
{:#communication-within-vlans}

Alle Ressourcen in einem VLAN können kommunizieren; dies bedeutet jedoch nicht, dass sie standardmäßig kommunizieren. Es ist wichtig zu beachten, dass VLANs ein Konstrukt der OSI-Modellschicht 2 sind und dass Teilnetze und IPs ein Konstrukt der Schicht 3 sind. Die Kommunikation wird auf jeder Schicht unterschiedlich ausgeführt. Ressourcen in verschiedenen VLANs, ob im öffentlichen oder privaten Netz, können nicht über Methoden der Schicht 2 miteinander kommunizieren.

### Kommunikation in einem VLAN im öffentlichen Netz
{:#communication-within-vlans-public}

Es gibt keine inhärenten Einschränkungen für die Kommunikation zwischen Ressourcen im öffentlichen Netz, sei es in einem oder mehreren VLANs in der öffentlichen Netzinfrastruktur von {{site.data.keyword.cloud}} oder im Internet. Einschränkungen können durch den Einsatz einer Firewall oder Gateway-Appliance hinzugefügt werden.

### Kommunikation in einem VLAN im privaten Netz
{:#communication-within-vlans-private}

Standardmäßig kann der Datenverkehr nur in demselben Teilnetz übertragen werden, selbst wenn sich mehrere Teilnetze in demselben VLAN befinden. Die Kommunikation mit anderen Teilnetzen in demselben VLAN ist jedoch möglich, wenn die Recheninstanzen über Routeneinträge für die weiteren Teilnetze in diesem VLAN verfügen. Die Verwaltung von Routeneinträgen auf allen Rechenknoten, die über private Teilnetze hinweg kommunizieren müssen, kann umständlich sein. Informationen zu Situationen, in denen die Standardkommunikation für den gesamten Datenverkehr in demselben VLAN erforderlich ist, finden Sie unter [VLAN-Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Beachten Sie, dass das VLAN-Spanning weitreichende Auswirkungen mit sich bringt und diese vor seiner Aktivierung sorgfältig überprüft werden müssen.

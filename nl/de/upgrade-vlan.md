---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Upgrade für automatisches VLAN durchführen
{:#upgrading-automatic-vlan}

Wenn Sie ein automatisches VLAN für eine Lösung eingerichtet haben, später aber wünschen, dass das VLAN über die Funktionen eines Premium-VLAN verfügen soll, können Sie ein Upgrade durchführen. Das Upgrade kann nicht rückgängig gemacht werden. Das VLAN wird zu einem Premium-VLAN und verbleibt bis zur Stornierung im Konto; zum Zeitpunkt der Stornierung wird es freigegeben.

Die Durchführung von Upgrades für VLANs ist nicht immer möglich. Es gelten weiterhin Einschränkungen für die VLAN-Kapazität.

Derzeit ist die Durchführung von Upgrades nur über die API möglich. Zwei Methoden stehen zur Verfügung:

  1. Aufgeben einer Bestellung unter Verwendung von `SoftLayer_Product_Order.placeOrder`.
  2. Verwendung der Schnellschnittstelle `SoftLayer_Network_Vlan.upgrade`.

## Aufgeben einer Bestellung
{:#place-vlan-order}

  1. Erstellen Sie eine Bestellung, die einer Bestellung für ein typisches Premium-VLAN ähnelt; achten Sie insbesondere auf das richtige Paket und die richtige Preisgestaltung.
  1. Entfernen Sie die Eigenschaften für `Position` und `Router-ID`, die für die Bestellung eines neuen Premium-VLAN erforderlich sind.
  1. Fügen Sie die Eigenschaft für die `ID` hinzu, und geben Sie den Wert von `SoftLayer_Network_Vlan.id` des VLANs an, für das das Upgrade durchgeführt werden soll.

## Schnellschnittstelle
{:#vlan-shortcut-interface}

Führen Sie die Operation [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) für ein vorhandenes VLAN aus, indem Sie den Aufruf mit dem Wert für `SoftLayer_Network_Vlan.id` des VLANs starten, für das das Upgrade durchgeführt werden soll. Auf diese Art werden die entsprechenden Paket- und Preisinformationen für das VLAN gesucht und die für die Durchführung des Upgrades erforderliche Bestellung wird aufgegeben. Bei Verwendung dieser Methode werden Bestellungen für VLAN-Upgrades nur aufgegeben, wenn das Konto für die automatische Auftragsgenehmigung qualifiziert ist.

Weitere Informationen finden Sie in der API-Dokumentation zu [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/).

## Nächste Schritte
{:#upgrade-vlan-what-happens-next}

Aus dem VLAN wird kurz nach dem Aufgeben einer erfolgreichen Bestellung ein Premium-VLAN.

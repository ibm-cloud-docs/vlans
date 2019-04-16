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


# VLAN-Spanning
{: #vlan-spanning}

Bei Verwendung des VLAN-Spanning können unabhängig von der Zuordnung der Geräte zum VLAN alle Geräte eines Kontos über das private Netz miteinander kommunizieren.
{: #shortdesc}

## Erläuterungen zum VLAN-Spanning
{: #understanding-vlan-spanning}


In {{site.data.keyword.Bluemix}} kann das VLAN-Spanning für viele verschiedene Zwecke verwendet werden und wirkt sich auf die Kommunikation der Geräte aus. Wenn Sie vor den ersten Schritten weitere Informationen zu den Grundlagen des VLAN-Spanning benötigen, überprüfen Sie die folgenden Informationen.
{: shortdesc}

### Funktionsweise des VLAN-Spanning
{: #how-vlan-spanning-works}

Wenn Sie das VLAN-Spanning aktivieren, kann der gesamte weitergeleitete Datenverkehr zwischen allen privaten Teilnetzen in alle privaten VLANs im Konto übertragen werden. Dies erfüllt Geschäftsanforderungen, für die die globale Kommunikation des weitergeleiteten Datenverkehrs erforderlich ist. Beispiel: Aktivieren Sie das VLAN-Spanning, wenn Geräte kommunizieren müssen, die Bestandteil mehrerer privater Teilnetze sind und gleichzeitig zu demselben oder einem anderen VLAN gehören.

Wenn das VLAN-Spanning aktiviert ist, wirkt sich dies auf das gesamte Konto aus. Sie können weder Teilnetze noch VLANs oder Geräte aus dem VLAN-Spanning ausschließen. Wenn Sie derzeit nur private Teilnetze verwenden, um Server in Rollen oder Tier zu trennen, wird diese Trennung durch die Aktivierung des VLAN-Spanning entfernt.{:note}

### Standardwerte
{: #vlan-spanning-default-values}

Das VLAN-Spanning ist standardmäßig inaktiviert. Zwischen Geräten, die sich in zwei verschiedenen privaten Teilnetzen befinden, kann unabhängig davon, ob sie Bestandteil desselben oder eines anderen VLANs sind, kein IP-Datenverkehr gesendet werden.

### Services, für die üblicherweise VLAN-Spanning erforderlich ist
{: #vlan-spanning-services}

Als Unterstützung für die Konfiguration des VLAN-Spanning stehen bestimmte Lernprogramm für Ihre Situation zur Verfügung. Informationen hierzu finden Sie unter den Links zu [Weitere Ressourcen](/docs/infrastructure/vlans?topic=vlans-other-resources-vlan-spanning).


## VLAN-Spanning verwalten
{: #manage-vlan-spanning}

Sie können das VLAN-Spanning für Ihr Konto aktivieren oder inaktivieren.
{: shortdesc}

Führen Sie die folgenden Schritte aus, um die Einstellungen für Ihr Konto zu aktualisieren:

  1. Öffnen Sie im Browser die [{{site.data.keyword.Bluemix_notm}}-Konsole ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://{DomainName}/){: new_window} und melden Sie sich bei Ihrem Konto an.
  2. Wählen Sie **Infrastruktur** im Menü aus. Das Kundenportal wird geöffnet.
  3. Wählen Sie über die Navigation des Kundenportals die Optionen **Netz > IP-Verwaltung > VLANs** aus.
  4. Wählen Sie die Registerkarte für **Spanning** aus, um auf den Abschnitt für VLAN-Spanning zugreifen zu können.
  5. Wählen Sie das Optionsfeld **Ein** oder **Aus** aus, um das VLAN-Spanning jeweils zu aktivieren oder zu inaktivieren.

Wenn Sie das VLAN-Spanning für einen kurzen Zeitraum wechseln, kann dies Anwendungsverzögerungen zur Folge haben.
{:note}

Die Verarbeitung der Aktualisierungsanforderung kann bis zu 15 Minuten dauern. Auf dem Bildschirm wird eine Bestätigung der Änderung angezeigt. Sie können die Einstellungen für das VLAN-Spanning jederzeit durch Wiederholen der oben beschriebenen Schritte aktualisieren.

---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-27"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# VLAN-Spanning aktivieren oder inaktivieren

Unter Umständen können sich mehrere private VLANs in einem einzigen Kundenkonto befinden. Netzeinheiten können jedoch im privaten Netz nicht miteinander kommunizieren, wenn sie sich nicht im selben VLAN befinden. VLAN-Spanning ermöglicht es allen Einheiten in einem Konto, unabhängig vom jeweils zugeordneten VLAN über das private Netz miteinander zu kommunizieren. 

Der Service des VLAN-Spanning gilt für alle Einheiten im Konto. Das Spanning kann nicht auf bestimmte VLANs oder auf bestimmte Einheiten angewendet werden. VLAN-Spanning kann nach Bedarf aktiviert oder inaktiviert werden und die Verarbeitung dauert ungefähr 15 Minuten nach dem Ändern der Einstellung. Führen Sie die in diesem Abschnitt beschriebenen Schritte aus, um VLAN-Spanning für ein Konto zu aktivieren oder zu inaktivieren.


1. Öffnen Sie über Ihren Browser das [Kundenportal ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](https://control.softlayer.com/){: new_window} und melden Sie sich an Ihrem Konto an.
2. Wählen Sie über die Navigation des Kundenportals die Optionen **Netz > IP-Verwaltung > VLANs** aus.
3. Wählen Sie die Registerkarte für **Spanning** aus, um auf den Abschnitt für VLAN-Spanning zugreifen zu können.
4. Wählen Sie das Optionsfeld **Ein** aus, um VLAN-Spanning zu aktivieren. Wählen Sie das Optionsfeld **Aus** aus, um VLAN-Spanning zu inaktivieren.

## Nächste Schritte

Nach dem Aktualisieren der Optionen für VLAN-Spanning kann die Verarbeitung der Anforderung bis zu 15 Minuten dauern. Eine Bestätigung der Änderung wird unterhalb der Registerkarte für Spanning angezeigt. Wenn Sie VLAN-Spanning aktivieren, können Einheiten VLAN-übergreifend über das private Netz miteinander kommunizieren. Inaktivieren Sie das Spanning, können Einheiten nur eine Verbindung zueinander herstellen, wenn sie sich im selben VLAN befinden. Die VLAN-übergreifende Kommunikation ist nicht mehr aktiviert. Die Einstellungen für VLAN-Spanning können durch Wiederholen der in diesem Abschnitt beschriebenen Schritte jederzeit aktualisiert werden. **Hinweis:** Das Umschalten zwischen VLAN-Spanning-Einstellungen innerhalb kurzer Zeit kann zu Verzögerungen bei der Anwendung der Einstellungen führen.

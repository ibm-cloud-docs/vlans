---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-27"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Abilita o disabilita lo spanning della VLAN

Alcune volte, più VLAN di rete private possono esistere su un solo account del cliente. Tuttavia, i dispositivi di rete non possono comunicare tra loro nella rete privata se non sono sulla stessa VLAN. Lo spanning della VLAN consente a tutti i dispositivi in un account di comunicare tra loro tramite la rete privata, indipendentemente dalla propria VLAN assegnata. 

Il servizio di spanning della VLAN si applica a tutti i dispositivi nell'account; non può essere applicato a VLAN o dispositivi specifici. Lo spanning della VLAN può essere abilitato o disabilitato quando necessario ed impiega circa 15 minuti per l'elaborazione, dopo che è stata effettuata una modifica all'impostazione. Segui la procedura fornita in questo articolo per abilitare o disabilitare lo spanning della VLAN in un account.


1. Dal tuo browser, apri il [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){: new_window} e accedi al tuo account.
2. Nella navigazione del Customer Portal, seleziona **Network > IP Management > VLANs**.
3. Seleziona la scheda **Span** per accedere alla sezione dello spanning della VLAN.
4. Seleziona il pulsante di opzione **On** per abilitare lo spanning della VLAN. Scegli il pulsante di opzione **Off** per disabilitare lo spanning della VLAN.

## Operazioni successive

Dopo aver aggiornato le selezioni dello spanning della VLAN, l'elaborazione della richiesta può impiegare fino a 15 minuti. Verrà visualizzata una conferma della modifica nella scheda Span. Se abiliti lo spanning della VLAN, i dispositivi possono comunicare tra loro nelle VLAN utilizzando la rete privata. Se disabiliti lo spanning, i dispositivi possono collegarsi tra loro solo se risiedono nella stessa VLAN; la comunicazione tra VLAN non è più abilitata. Le impostazioni dello spanning della VLAN possono essere aggiornate in qualsiasi momento ripetendo la procedura fornita in questo articolo. **Nota:** l'attivazione/disattivazione delle impostazioni dello spanning della VLAN in un breve lasso di tempo, può causare un ritardo dell'applicazione delle impostazioni.

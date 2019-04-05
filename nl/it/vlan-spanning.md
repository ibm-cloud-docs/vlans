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


# VLAN Spanning
{: #vlan-spanning}

Lo spanning della VLAN consente a tutti i dispositivi in un account di comunicare tra loro tramite la rete privata, indipendentemente dalla VLAN assegnata ai dispositivi.
{: #shortdesc}

## Informazioni sullo spanning della VLAN
{: #understanding-vlan-spanning}


In {{site.data.keyword.Bluemix}}, lo spanning della VLAN può essere utilizzato per molti scopi diversi e influisce sulla comunicazione dei dispositivi. Per saperne di più sulle nozioni di base dello spanning della VLAN prima di iniziare, consulta le seguenti informazioni.
{: shortdesc}

### Come funziona lo spanning della VLAN
{: #how-vlan-spanning-works}

Lo spanning della VLAN consente di trasmettere tutto il tuo traffico indirizzato tra tutte le sottoreti private, attraverso tutte le VLAN private sul tuo account. Questo soddisfa le esigenze aziendali che richiedono la comunicazione globale del tuo traffico instradato. Ad esempio, è possibile abilitare lo spanning della VLAN se i dispositivi che risiedono su più di una sottorete privata devono comunicare, sia sulla stessa VLAN che su VLAN diverse.

Quando lo spanning è abilitato, influisce sull'intero account. Non puoi escludere sottoreti, VLAN o dispositivi dallo spanning della VLAN. Se attualmente ti basi esclusivamente sulle sottoreti private per segregare i server in ruoli o livelli, l'abilitazione dello spanning della VLAN rimuove tale segregazione.
{:note}

### Valori predefiniti
{: #vlan-spanning-default-values}

Per impostazione predefinita, lo spanning di VLAN è disabilitato. I dispositivi situati su due diverse sottoreti private, sia sulla stessa VLAN che su VLAN diverse, non saranno in grado di inviare traffico IP tra di loro.

### Servizi che in genere richiedono lo spanning della VLAN
{: #vlan-spanning-services}

Sono disponibili esercitazioni specifiche per aiutarti a configurare lo spanning della VLAN per la tua situazione. Vedi i nostri link in [Altre risorse](/docs/infrastructure/vlans?topic=vlans-other-resources-for-vlan-spanning).


## Gestione dello spanning della VLAN
{: #manage-vlan-spanning}

Puoi abilitare o disabilitare lo spanning della VLAN per il tuo account.
{: shortdesc}

Per aggiornare l'impostazione del tuo account, segui questa procedura:

  1. Dal tuo browser, apri la [console {{site.data.keyword.Bluemix_notm}} ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/){: new_window} e accedi al tuo account.
  2. Nel menu, seleziona **Infrastructure**. Si apre il Customer Portal.
  3. Nella navigazione del Customer Portal, seleziona **Network > IP Management > VLANs**.
  4. Seleziona la scheda **Span** per accedere alla sezione di VLAN Spanning.
  5. Seleziona il pulsante di opzione **On** o **Off** secondo necessità per abilitare o disabilitare lo spanning della VLAN.

L'attivazione/disattivazione dello spanning della VLAN in un breve lasso di tempo potrebbe comportare ritardi nell'applicazione.
{:note}

L'elaborazione della richiesta di aggiornamento può richiedere fino a 15 minuti. Una conferma della modifica viene visualizzata sullo schermo. Puoi aggiornare le impostazioni dello spanning della VLAN in qualsiasi momento ripetendo i passi precedenti.

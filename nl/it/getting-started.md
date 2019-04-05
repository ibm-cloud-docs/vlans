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

# Introduzione alle VLAN
{:#getting-started-with-vlans}

Le VLAN (Virtual Local Area Network) vengono utilizzate da {{site.data.keyword.cloud}} per isolare il traffico di broadcast sulle reti pubbliche e private. Le VLAN vengono assegnate in base alle necessità per soddisfare le altre offerte. Ad esempio, se effettui un ordine di calcolo per un data center in cui non sei ancora presente, ricevi automaticamente una VLAN. Gli ordini di calcolo aggiuntivi per lo stesso data center, che non specificano i requisiti di rete, vengono generalmente effettuati nella VLAN precedentemente assegnata. Tutte le VLAN assegnate automaticamente vengono anche rimosse automaticamente quando non sono più necessarie per le tue risorse.

Le VLAN sono specifiche per i router utilizzati nei data center IBM Cloud e un data center contiene più router sia per le reti pubbliche che private. Pertanto, è possibile che più VLAN possano essere assegnate all'interno di un singolo data center. È anche possibile ordinare VLAN aggiuntive per costruire topologie di rete più complesse, tipicamente in combinazione con un [Virtual Router Appliance](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance).

Facciamo riferimento alle VLAN acquistate come **VLAN premium** e alle VLAN gestite automaticamente da {{site.data.keyword.cloud}} come **VLAN automatiche**. Scopri di più sul funzionamento delle VLAN in [Informazioni sulle VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans).


## Gestione delle VLAN
{:#managing-vlans}

Segui questi passi per riesaminare le VLAN sul tuo account.

  1. Apri la [Console IBM Cloud ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/){: new_window} e accedi al tuo account.
  2. Nel menu, seleziona **Infrastructure**.
  3. Nella navigazione del Customer Portal, seleziona **Network > IP Management > VLANs**.

L'elenco delle VLAN visualizza informazioni sulle tue VLAN e fornisce l'accesso a ciascuna di esse, insieme ai dispositivi o sottoreti associati.

### Comprensione della selezione tra pod e data center
{:#pod-vs-datacenter-selection}

Le opzioni per dove ordinare una VLAN forniscono esigenze e vincoli diversi. Questa sezione riepiloga i motivi per cui potresti selezionare un'opzione rispetto a un'altra.

L'opzione **Order by Pod** ti consente di specificare il pod esatto (e quindi il router) in cui hai bisogno di una VLAN. Utilizza questa opzione se hai un motivo specifico per cui la VLAN debba esistere in quel pod. I motivi includono l'utilizzo della VLAN con un dispositivo gateway o un firewall a più VLAN esistente. In genere, se ordini VLAN aggiuntive come parte di uno schema di distribuzione più grande, conosci il pod in cui desideri inserire le VLAN. Se è così, scegli questa opzione.

Utilizza l'opzione **Order by Datacenter** se l'ubicazione della VLAN è meno importante. Questa è l'opzione migliore se vuoi selezionare un'ubicazione per la quale raggrupperai altre risorse. Se le tue distribuzioni seguono una strategia per dare priorità alla rete (anziché ordinare prima i server), l'utilizzo di questa opzione per stabilire la tua presenza in un nuovo data center offre la migliore esperienza possibile. Le tue VLAN richieste vengono soddisfatte da qualsiasi pod nel data center selezionato; non ci sono previsioni su quale pod verrà selezionato quando scegli questa opzione.

Consigliamo di utilizzare l'opzione di ubicazione meno specifica disponibile che soddisfi le tue attuali esigenze.

### Ordini complessi
{:#complex-orders-vlans}

L'esperienza di ordine sul portale consente di ordinare solo una singola configurazione VLAN per ciascun ordine. Una configurazione è costituita dalla rete, dall'opzione di ubicazione e dalla quantità desiderata. Mentre è possibile ordinare più configurazioni VLAN in un singolo ordine tramite l'API, ogni quantità di configurazione è limitata a 1. Ciò significa che ciascuna configurazione VLAN fornita viene soddisfatta in modo indipendente. Pertanto, se ciascuna configurazione utilizza l'opzione relativa all'ubicazione del data center, ciascuna VLAN può essere assegnata a pod diversi all'interno di quel data center.

### Una nota sulla capacità
{:#note-about-capacity}

Un tentativo di ordinare una VLAN potrebbe essere impedito a causa di limitazioni di capacità nell'ubicazione selezionata. In tale circostanza, vengono interessati tutti gli utenti che tentano di ordinare le VLAN in quella ubicazione; non è disponibile alcun ricorso. Se possibile, ti consigliamo di stabilire una presenza in un altro data center e di prendere in considerazione l'opportunità di utilizzare [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Se le tue esigenze di ubicazione sono flessibili, è più opportuno utilizzare l'opzione di ubicazione meno specifica quando ordini le VLAN, in quanto ciò consente una maggiore flessibilità nell'allocazione delle tue VLAN. Inoltre, la capacità della VLAN in un'ubicazione tentata precedentemente può diventare disponibile in un secondo momento.


## Annullamento delle VLAN premium
{:#canceling-premium-vlans}

Quando sei pronto a rimuovere una VLAN premium, individua tale VLAN nell'elenco di VLAN del tuo account (vedi Gestione delle VLAN in alto) e fai clic sull'icona "X" all'interno della voce per avviare le richieste di annullamento.

Non è possibile annullare le VLAN premium se sono utilizzate da altri prodotti. I seguenti usi impediscono l'annullamento:

  * Server disponibili direttamente sulla VLAN (anziché con collegamento trunk).
  * Sottoreti secondarie instradate alla VLAN o un indirizzo IP sulla VLAN.
  * Prodotti firewall che servono l'intera VLAN. Ciò esclude, ad esempio, i firewall hardware non dedicati.
  * Associazione a un gruppo di ridimensionamento automatico.
  * Collegamento trunk ai server (questo utilizzo cambierà in futuro).

Inoltre, alcuni prodotti e funzioni **non impediranno l'annullamento** di una VLAN, ma saranno influenzati dalla sua rimozione. Ciò include:

  * Essere protetti da un Virtual Router Appliance. L'associazione della VLAN verrà rimossa indipendentemente dal fatto che sia ignorata o meno.

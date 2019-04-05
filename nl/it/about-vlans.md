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

# Informazioni sulle VLAN
{:#about-vlans}

Le VLAN sono fondamentali per indirizzare il traffico verso le tue risorse. Potresti non dover mai interagire direttamente con le VLAN in quanto sono gestite automaticamente: vengono assegnate in base alle esigenze e rimosse quando non sono più necessarie.

Una VLAN è un concetto di rete. Ti consente di creare domini di broadcast al livello 2 del [modello OSI ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://en.wikipedia.org/wiki/OSI_model), il _livello di collegamento dati_. Le VLAN forniscono un unico metodo di identificazione dei pacchetti e consentono la coesistenza di più carichi di lavoro sulla stessa
apparecchiatura fisica. Per ulteriori informazioni sulle VLAN, fai riferimento a [questo articolo ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://en.wikipedia.org/wiki/Virtual_LAN).

## Tipi di VLAN
{:#types-of-vlans}

Esistono due tipi distinti di VLAN che {{site.data.keyword.cloud}} definisce come **Automatiche** e **Premium**. Ciascuna di queste VLAN ha un ruolo diverso ed è importate comprenderne le differenze.

### VLAN automatiche
{:#automatic-vlans}

Le VLAN automatiche sono gestite da {{site.data.keyword.cloud}} automaticamente; vengono assegnate e rimosse secondo necessità per soddisfare le esigenze degli altri prodotti che ordini. Solitamente, hai una VLAN automatica per ciascun router. Le VLAN automatiche vengono associate ai server ordinati senza una specifica VLAN selezionata. Non è possibile ordinare o annullare le VLAN automatiche, perché sono presenti sul tuo account solo quando i nostri sistemi stabiliscono che sono necessarie e vengono quindi rimosse quando gli stessi sistemi stabiliscono che non lo sono più.

### VLAN premium
{:#about-premium-vlans}

Le VLAN premium vengono acquisite ordinando una VLAN. Per istruzioni, vedi [Ordine di VLAN premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans). Le VLAN premium rimangono sul tuo account fino a quando non vengono esplicitamente annullate. Puoi ordinare tutte le VLAN premium che desideri, in base ai limiti di capacità. Nel caso in cui la capacità non sia disponibile, cerca le VLAN in un altro pod o data center.

Una distinzione importante delle VLAN premium è che non vengono selezionate automaticamente per adempiere un ordine del server. Le VLAN premium devono essere selezionate esplicitamente durante il processo di ordine del server per far sì che i server risiedano su di esse. Consulta la [FAQ](/docs/infrastructure/vlans?topic=vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-) per istruzioni sulla selezione della VLAN.


## Identificazione della VLAN
{:#vlan-identification}

Le VLAN si trovano sui router all'interno dei data center IBM Cloud. Ogni VLAN è identificata da una combinazione univoca di numero, router e ubicazione del data center. Ad esempio, la `VLAN 829` pubblica, che si trova sul router `fcr02` nel data center `SJC01`, è identificata con `sjc01.fcr02.829`. La VLAN 2234 privata, ubicata sul router `bcr01` nel data center `AMS01`, è identificata con `ams01.bcr01.2234`.


## VLAN e sottoreti
{:#vlans-subnets}

Le VLAN possono contenere una o più sottoreti. Come le VLAN, alcune sottoreti vengono aggiunte e rimosse automaticamente man mano che i dispositivi richiedono indirizzi IP. Ulteriori dettagli su quali sottoreti possono esistere e su come funzionano sono disponibili in [Sottoreti e IP](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips).


## Comunicazione all'interno di una VLAN
{:#communication-within-vlans}

Per impostazione predefinita, tutte le risorse su una VLAN possono comunicare, ma ciò non significa che lo faranno. È importante ricordare che le VLAN sono un costrutto di livello 2 del modello OSI e che le sottoreti e gli IP sono un costrutto di livello 3. La comunicazione avviene in modo diverso a ogni livello. Le risorse presenti in VLAN diverse, sia sulla rete pubblica che privata, non possono comunicare tra loro tramite i metodi del livello 2.

### Comunicazione all'interno di una VLAN sulla rete pubblica
{:#communication-within-vlans-public}

Non esistono limitazioni intrinseche alla comunicazione tra le risorse sulla rete pubblica, sia su una o più VLAN all'interno dell'infrastruttura di rete pubblica di {{site.data.keyword.cloud}} sia su Internet. È possibile aggiungere delle limitazioni introducendo un firewall o un dispositivo gateway.

### Comunicazione all'interno di una VLAN sulla rete privata
{:#communication-within-vlans-private}

Per impostazione predefinita, solo le istanze di calcolo all'interno della stessa sottorete possono comunicare, anche se più sottoreti si trovano nella stessa VLAN. Tuttavia, è possibile comunicare con altre sottoreti sulla stessa VLAN purché le istanze di calcolo abbiano voci di rotta per
le sottoreti aggiuntive su tale VLAN. La gestione delle voci di rotta su tutti i nodi di calcolo che devono comunicare tra le sottoreti private può essere complicata. Per le situazioni in cui è richiesta la comunicazione predefinita tra tutte le istanze di calcolo all'interno della stessa VLAN, vedi [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Nota che la funzione VLAN Spanning ha ampie implicazioni e deve essere esaminata attentamente prima di abilitarla.

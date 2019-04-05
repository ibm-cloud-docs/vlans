---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: new VLAN, subnet selector, VLAN moves

subcollection: vlans

---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}
{:faq: data-hd-content-type='faq'}

# FAQ
{:#vlans-faqs}


## Posso spostare un dispositivo esistente in una nuova VLAN?
{: faq}

I dispositivi esistenti possono essere spostati ad altre VLAN, ma solo quando viene richiesto lo spostamento. Poiché le VLAN sono correlate a un router e le connessioni ad ogni router dipendono dall'ubicazione fisica del dispositivo, alcuni spostamenti di VLAN possono richiedere anche una ricollocazione fisica. Questo è sempre il caso in cui la nuova VLAN viene ubicata in un data center differente, ma si può anche applicare quando sposti un dispositivo a una VLAN differente nello stesso data center. Effettuando questo spostamento si interrompe la connettività di rete ed è necessaria la modifica dell'indirizzo IP del dispositivo quando la connessione viene spostata alla nuova VLAN. Quando sposti un dispositivo a una nuova VLAN richiediamo che sia consentita un'ampia pianificazione, perché la macchina sarà offline per la durata dello spostamento.


## Esiste un modo per specificare quale VLAN voglio utilizzare per il mio dispositivo quando lo ordino?
{: faq}

Sì, è possibile selezionare una VLAN specifica durante il processo di ordine. Quando ordini un dispositivo, questa opzione è disponibile alla fine del modulo d'ordine. Viene selezionata una VLAN privata, seguita da una pubblica. Nota inoltre che, per ogni VLAN, viene presentato un selettore di sottorete; questa selezione è **facoltativa**. Seleziona una sottorete solo se hai un motivo per farlo, in quanto la selezione di una sottorete priva di indirizzi IP disponibili avrà un impatto negativo sull'adempimento ordini del dispositivo (per ulteriori dettagli, consulta la [FAQ relativa alla sottorete](/docs/infrastructure/subnets?topic=subnets-subnets-faq)).

È importante notare che la VLAN selezionata deve essere ubicata nello stesso data center del dispositivo. Non possiamo assegnare un dispositivo a una VLAN ubicata in un data center differente.


## Quanti dispositivi possono essere assegnati a una sola VLAN?
{: faq}

Attualmente non esiste alcun limite per il numero di dispositivi che vengono associati a una singola VLAN in qualsiasi momento; tuttavia, quando un firewall hardware è associato a una VLAN, il tipo di firewall può imporre restrizioni sul numero di dispositivi che
risiedono sulla VLAN.


## Quali tipi di dispositivi vengono assegnati a una VLAN?
{: faq}

Tutti i dispositivi con una connessione di rete saranno associati a una VLAN. I server dedicati dispongono sia di una connessione di rete pubblica che privata, per cui vedrai questi dispositivi associati alle VLAN pubbliche e private.

## Come creo un trunk dalle mie VLAN ai miei server?
{: faq}

È possibile creare un trunk dalle VLAN ai server bare metal solo attraverso l'uso dell'API; per questa attività non è disponibile alcuna interfaccia del portale.
Per ulteriori informazioni sulla gestione delle VLAN come trunk, consulta i link alla documentazione API elencati di seguito.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## Quando ordino una VLAN, cosa significa quando mi viene detto che non ci sono VLAN disponibili?
{: faq}

Vedi [Una nota sulla capacità](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity).


## Perché i miei dispositivi non possono comunicare tra loro sulla stessa VLAN privata?
{: faq}

Se ciascun server si trova su una sottorete diversa, per impostazione predefinita non sarà in grado di comunicare tramite gli indirizzi IP. Tecnicamente, i tuoi server possono comunicare utilizzando i metodi di livello 2 del modello OSI perché si trovano sulla stessa VLAN (un costrutto di livello 2). Per il funzionamento della comunicazione IP (Internet Protocol) (chiamato anche livello 3), puoi aggiungere una rotta per la sottorete con cui stai tentando di comunicare su ciascun server (la rotta è diversa su ciascun server) o abilitare la funzione [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Nota che [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) ha ulteriori implicazioni, quindi esamina la funzione in dettaglio prima di decidere di abilitarla.


## Quali opzioni sono disponibili se ho bisogno che dispositivi su sottoreti private diverse all'interno della stessa VLAN comunichino per impostazione predefinita, ma non voglio abilitare VLAN Spanning?
{: faq}

Comprendiamo che gestire le rotte sui server sia complicato considerando che {{site.data.keyword.cloud}} assegna e rimuove automaticamente le sottoreti primarie secondo necessità. Comprendiamo anche che non è sempre possibile ricorrere alla funzione [VLAN Spanning](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Se hai una distribuzione di grandi dimensioni che è ostacolata da questo comportamento, puoi richiedere una sottorete primaria adeguata solo su una
[VLAN premium](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans). Verranno applicati addebiti per questa sottorete e possono variare a seconda della richiesta. È a nostra discrezione concedere o negare tali richieste caso per caso (non in base all'account, bensì in base ad ogni richiesta). Segui queste istruzioni per richiedere una sottorete primaria di dimensioni specifiche:

  1. Apri la [Console IBM Cloud ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://{DomainName}/){: new_window} e accedi al tuo account.
  1. Nel menu, seleziona **Classic Infrastructure**.  
  1. Nel menu di navigazione dell'infrastruttura classica, seleziona **Network > IP Management > VLANs**.
  1. Ordina una VLAN premium, se necessario. Vedi [Ordine di VLAN premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans).
  1. Apri un ticket passando a **Support > Add Ticket** nel menu.
    - Oggetto: "Private Network Question" o "Public Network Question"
    - Titolo: "Large Primary Subnet Request"
    - Dettagli: specifica la VLAN premium desiderata per la sottorete utilizzando la notazione datacenter.router.vlan (ad esempio, ams03.bcr01.1234). Quindi specifica la dimensione della sottorete desiderata nella notazione CIDR (ad esempio, /25). Indica quanti server prevedi di acquistare e in quale periodo di tempo. Inoltre, spiega in che modo il tuo utilizzo potrebbe essere ostacolato senza la sottorete richiesta. Spiega in modo dettagliato come la tua situazione potrebbe essere ostacolata, perché questo input ci aiuta a valutare i miglioramenti per la nostra piattaforma. Non verranno prese in considerazione altre proprietà della sottorete, per cui non è necessario specificare ulteriori specifiche.

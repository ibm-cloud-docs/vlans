---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-17"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# FAQ


## Posso spostare un dispositivo esistente in una nuova VLAN?

I dispositivi esistenti possono essere spostati ad altre VLAN, ma solo quando viene richiesto lo spostamento. Poiché le VLAN sono correlate a un router e le connessioni ad ogni router dipendono dall'ubicazione fisica del dispositivo, alcuni spostamenti di VLAN possono richiedere anche una ricollocazione fisica. Questo è sempre il caso in cui la nuova VLAN viene ubicata in un data center differente, ma si può anche applicare quando sposti un dispositivo a una VLAN differente nello stesso data center. Effettuando questo spostamento si interrompe la connettività di rete ed è necessaria la modifica dell'indirizzo IP del dispositivo quando la connessione viene spostata alla nuova VLAN. Quando sposti un dispositivo a una nuova VLAN richiediamo che sia consentita un'ampia pianificazione, perché la macchina sarà offline per la durata dello spostamento.


## Esiste un modo per specificare quale VLAN voglio utilizzare per il mio dispositivo quando lo ordino?

Sì, può essere specificata una VLAN durante il processo di ordine. Quando ordini un dispositivo, questa opzione è disponibile alla fine del modulo d'ordine. Viene selezionata una VLAN privata, seguita da una pubblica. È importante notare che la VLAN deve essere ubicata nello stesso data center del dispositivo. Non possiamo assegnare un dispositivo a una VLAN ubicata in un data center differente.

## Quanti dispositivi possono essere assegnati a una sola VLAN?

Al momento non c'è limite al numero di dispositivi che vengono associati a una sola VLAN; tuttavia, quando un firewall hardware viene associato alla VLAN, le regole del firewall possono imporre delle limitazioni al numero di dispositivi che risiedono nella VLAN.

## Le VLAN funzionano sia sulla rete pubblica che privata?

Sì, esistono sia VLAN pubbliche che private. In molti casi, un dispositivo che ha sia--una connessione pubblica che privata-- avrà una connessione sia nella VLAN pubblica che privata.

## Quali tipi di dispositivi vengono assegnati a una VLAN?

Tutti i dispositivi con una connessione di rete saranno associati a una VLAN. I server dedicati hanno sia una connessione di rete privata che pubblica, per cui vedrai questi dispositivi associati alle VLAN pubblica e privata (una VLAN per tipo di connessione, per dispositivo).

I firewall hardware funzionano in modo leggermente differente: vengono posizionati davanti a una VLAN per intercettare e filtrare il traffico. Questi dispositivi sono correlati alla VLAN che li utilizza, ma al momento non risiedono nella VLAN stessa.

---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-20"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Introduzione alle VLAN

Una VLAN è una rete dell'area locale virtuale, che può essere creata per consentire ai clienti di separare le parti di una rete molto grande in sottoreti più piccole. Una VLAN funziona come un contenitore in cui gli indirizzi IP e le connessioni di un solo cliente possono rimanere separate da tutti gli altri clienti. Le VLAN permettono una migliore sicurezza e l'isolamento di alcuni problemi. Nella nostra rete {{site.data.keyword.BluSoftlayer_notm}}, le VLAN forniscono la capacità di partizionare i tuoi dispositivi e sottoreti. 

Puoi gestire le tue VLAN dalla schermata della VLAN:

1. Dal tuo browser, apri il [Customer Portal ![Icona link esterno](../../icons/launch-glyph.svg "Icona link esterno")](https://control.softlayer.com/){: new_window} e accedi al tuo account.
2. Nella navigazione del Customer Portal, seleziona **Network > IP Management > VLANs**.

La schermata delle VLAN visualizza le informazioni sulle tue VLAN e ti fornisce l'accesso ad ognuna di esse, insieme ai dispositivi o sottoreti associati. Come viene aggiunto un servizio, i clienti possono abilitare lo spanning della VLAN, che collega tutte le VLAN di rete private a un account, così consentendo ai dispositivi su VLAN separate di comunicare tra loro. 

## Identificazione della VLAN

Le VLAN si trovano nei router nei nostri data center. Ogni VLAN viene identificata da un numero, un router e un'ubicazione data center univoci. Ad esempio, `VLAN 829`, ubicata nel router `fcr02` nel data center `SJC01` viene identificata dal nostro sistema come `829 fcr02.sjc01`.

## Spanning della VLAN

Lo spanning della VLAN è una configurazione dell'account che consente l ospostamento del traffico tra le VLAN private che appartengono a un solo account. A causa della natura della rete privata, è consentito molto poco traffico nelle VLAN privare di un account. In generale, le VLAN proteggono i dispositivi dal traffico di rete di altri account del cliente. Le VLAN private portano questa protezione una fase più avanzata, limitando il traffico sulla VLAN a quello che si verifica tra i dispositivi su tale VLAN; pertanto, per impostazione predefinita, i dispositivi ubicati su due VLAN private differenti non possono inviare il traffico tra loro. Con l'[abilitazione dello spanning della VLAN](vlan-spanning.html), questa limitazione viene eliminata in modo che i dispositivi su VLAN private differenti di un account possano comunicare.

### Quando dovrei abilitare lo spanning della VLAN per il mio account?

Lo spanning della VLAN dovrebbe venire abilitato se si verificano bisogni di business. Ad esempio, se i server che risiedono su più di una sottorete privata devono comunicare, lo spanning della VLAN dovrebbe essere abilitato. La comunicazione tra le VLAN non è specifica per l'ubicazione fisica della VLAN; ad esempio, le VLAN private nello stesso data center sono ancora completamente separate tra loro. Quando i dispositivi sono ubicati in due o più VLAN, ognuno con la propria sottorete, lo spanning della VLAN deve essere abilitato per la comunicazione dei dispositivi.

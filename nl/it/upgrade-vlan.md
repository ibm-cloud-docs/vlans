---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Upgrade di una VLAN automatica
{:#upgrading-automatic-vlan}

Se hai creato una soluzione attorno a una VLAN automatica e in seguito decidi che vuoi avere le funzionalità di una VLAN premium, puoi eseguirne l'upgrade. L'upgrade non è reversibile. La VLAN diventa una VLAN premium e rimane sul tuo account finché non viene annullata; a quel punto verrà recuperata.

L'upgrade delle VLAN non è sempre possibile. Valgono ancora le limitazioni di capacità della VLAN.

Per il momento, l'upgrade è disponibile solo tramite l'API. Per questa operazione, sono disponibili due metodi:

  1. Effettuare un ordine utilizzando `SoftLayer_Product_Order.placeOrder`.
  2. Utilizzare l'interfaccia di scelta rapida `SoftLayer_Network_Vlan.upgrade`.

## Effettuazione di un ordine
{:#place-vlan-order}

  1. Costruisci un ordine simile a una tipica VLAN premium, in particolare con il pacchetto e il prezzo corretti.
  1. Rimuovi le proprietà `location` e `routerId` che sono richieste quando si ordina una VLAN premium.
  1. Aggiungi la proprietà `id` e compilala con il valore `SoftLayer_Network_Vlan.id` della VLAN di cui eseguire l'upgrade.

## Interfaccia di scelta rapida
{:#vlan-shortcut-interface}

Esegui l'operazione [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) su una VLAN esistente inizializzando la chiamata con il valore `SoftLayer_Network_Vlan.id` della VLAN di cui eseguire l'upgrade. Questa operazione individua le informazioni su pacchetto e prezzo appropriate per la VLAN ed effettua l'ordine necessario per eseguire l'upgrade. Utilizzando questo metodo, gli ordini di upgrade della VLAN verranno effettuati solo se il tuo account è idoneo per l'approvazione automatica degli ordini.

Per ulteriori dettagli, consulta la documentazione API per [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/).

## Operazioni successive
{:#upgrade-vlan-what-happens-next}

La VLAN viene passata a una VLAN premium subito dopo l'immissione corretta dell'ordine.

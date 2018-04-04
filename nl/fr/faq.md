---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-17"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Foire aux questions


## Puis-je déplacer une unité existante vers un nouveau réseau local virtuel ?

Les unités existantes peuvent être déplacées vers d'autres réseaux locaux virtuels à condition qu'une demande de transfert soit émise. Les réseaux locaux virtuels étant associés à un routeur, et les connexions à chacun de ces routeurs étant fonction de l'emplacement physique de l'unité, il se peut que le transfert de certains VLAN impose une réinstallation physique. Cela est toujours le cas lorsque le nouveau VLAN se trouve dans un autre centre de données, mais cela peut également s'avérer nécessaire lorsqu'une unité est transférée vers un autre VLAN du même centre de données. Ce type de transfert implique l'interruption de connectivité du réseau ainsi que la modification de l'adresse IP de l'unité lorsque la connexion est déplacée vers le nouveau réseau local virtuel. Dans le cadre d'un transfert d'unité vers un nouveau VLAN, un temps d'arrêt suffisant doit être planifié, car la machine est hors ligne pendant toute la durée du transfert.


## Est-il possible de spécifier le VLAN que je souhaite utiliser avec mon unité au moment de la commande ?

Oui, vous pouvez indiquer un VLAN spécifique lors du processus de commande. Lorsque vous commandez une unité, cette option est disponible à la fin du formulaire de commande. Un réseau VLAN privé est sélectionné, suivi d'un réseau VLAN public. Il est important de noter que le VLAN doit se trouver dans le même centre de données que l'unité. Nous ne pouvons pas affecter une unité à un VLAN qui se trouve dans un autre centre de données.

## Combien d'unités puis-je affecter à un seul réseau local virtuel ?

Il n'y a pas de limite au nombre d'unités pouvant être associées à un même réseau local virtuel. Toutefois, lorsqu'un pare-feu matériel est associé à un VLAN, les règles du pare-feu peuvent imposer une limite au nombre d'unités hébergées sur le VLAN.

## Les réseaux locaux virtuels fonctionnent-ils sur les réseaux public et privé ?

Oui, les deux réseaux VLAN public et privé sont disponibles. Dans la plupart des cas, une unité possède à la fois une connexion publique et une connexion privée, ce qui signifie que les communications seront établies à la fois sur le réseau local virtuel public et privé.

## Quels sont les types d'unités affectées à un réseau local virtuel ?

N'importe quelle unité dotée d'une connexion réseau peut être associée à un réseau local virtuel. Les serveurs dédiés disposant à la fois d'une connexion réseau publique et privée, vous verrez ces unités être affectés à la fois à des VLAN publics et privés (un VLAN par type de connexion, par unité).

Les pare-feux matériels fonctionnent un peu différemment : ils sont placés à l'avant d'un réseau local virtuel pour intercepter et filtrer le trafic. Ces unités sont liées au VLAN qu'elles desservent, sans résider réellement sur le VLAN en question.

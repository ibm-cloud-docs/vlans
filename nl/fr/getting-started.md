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

# Initiation aux VLAN
{:#getting-started-with-vlans}

Les réseaux locaux virtuels (VLAN) sont utilisés par {{site.data.keyword.cloud}} pour isoler le trafic diffusé sur le réseau public et le réseau privé. Ces réseaux sont affectés en fonction des besoins des autres offres. Par exemple, si vous effectuez une commande auprès d'un centre de données dans lequel vous n'êtes pas encore présent, vous recevez automatiquement un réseau virtuel local. Toutes les commandes supplémentaires, qui ne précisent pas les exigences réseaux, sont généralement placées dans le VLAN affecté précédemment. Tous les réseaux locaux virtuels affectés automatiquement sont également retirés automatiquement lorsque vos ressources n'en ont plus besoin.

Les VLAN sont spécifiques aux routeurs utilisés dans les centres de données IBM Cloud, et un centre de données comporte plusieurs routeurs pour les réseaux publics et privés. Par conséquent, plusieurs VLAN peuvent être affectés au sein d'un seul centre de données. Il est également possible de commander des VLAN supplémentaires afin de construire des topologies de réseaux plus complexes, souvent en association avec un [Dispositif de routeur virtuel](/docs/infrastructure/virtual-router-appliance?topic=virtual-router-appliance-getting-started-with-ibm-virtual-router-appliance).

Nous qualifions les VLAN que vous achetez de **VLAN Premium** et les VLAN qui sont gérés automatiquement par {{site.data.keyword.cloud}} de **VLAN automatiques**. Pour approfondir vos connaissances concernant le fonctionnement des VLAN, lisez la rubrique [A propos des VLAN](/docs/infrastructure/vlans?topic=vlans-about-vlans).


## Gestion de réseaux locaux virtuels
{:#managing-vlans}

Suivez les étapes ci-dessous pour voir les VLAN sur votre compte.

  1. Ouvrez la [console IBM Cloud ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/){: new_window} et connectez-vous à votre compte.
  2. Dans le menu, sélectionnez **Infrastructure**.
  3. Dans la navigation du portail client, sélectionnez **Réseau > Gestion IP > VLAN**.

La liste des VLAN affiche des informations sur vos réseaux locaux virtuels et permet d'accéder à chaque VLAN, de même que les unités ou sous-réseaux associés.

### Sélection de pod vs sélection de centre de données
{:#pod-vs-datacenter-selection}

Les options relatives à la source du VLAN répondent à des besoins et contraintes différents. La présente section résume les raisons pour lesquelles vous pouvez être amené à sélectionner l'une plutôt que l'autre.

L'option **Commande par pod** vous permet de spécifier le nombre exacts de pods (et donc de routeurs) pour lesquels vous avez besoin d'un réseau local virtuel. Choisissez cette option si vous avez une raison particulière d'héberger ce VLAN dans ce pod. Parmi les raisons possibles, citons l'utilisation du réseau local virtuel avec un dispositif de passerelle ou un pare-feu multi-VAN. D'habitude, si vous commandez des VLAN supplémentaires dans le cadre d'un schéma de déploiement plus important, vous savez déjà dans quel pod vous voulez installer les VLAN. Dans ce cas, choisir cette option constitue la meilleure solution.

L'option **Commande par centre de données** est adaptée lorsque l'emplacement du réseau local virtuel a moins d'importance. Choisissez cette option si vous voulez utiliser un emplacement comme point de départ à partir duquel ajouter d'autres ressources. Si vos déploiements suivent une stratégie basée d'abord sur les réseaux (par opposition à une stratégie basée d'abord sur la commande de serveurs), l'utilisation de cette option pour établir votre présence dans un nouveau centre de données constitue la meilleure solution. Les VLAN que vous demandez sont pris en charge par n'importe quel pod du centre de données sélectionné, sans possibilité de choix, lorsque vous sélectionnez cette option.

Il est préférable d'utiliser l'option d'emplacement disponible la moins spécifique, qui répond à votre besoin actuel.

### Commandes complexes
{:#complex-orders-vlans}

Le portail permet uniquement de commander une configuration VLAN à la fois. Une configuration est constituée du réseau choisi, de l'option d'emplacement et de la quantité. Bien qu'il soit possible de commander plusieurs configurations VLAN lors d'une même commande via l'API, chaque quantité de configuration est limitée à 1. Autrement dit, chaque configuration VLAN fournie est prise en charge de manière indépendante. Par conséquent, si chaque configuration utilise l'option d'emplacement de centre de données, chaque réseau local virtuel peut être affecté à des pods différents du centre de données.

### Remarque relative à la capacité
{:#note-about-capacity}

Une tentative de commande d'un réseau local virtuel peut être bloquée en raison de restrictions de capacité au niveau de l'emplacement sélectionné. Si cela se produit, tous les utilisateurs qui essaient de commander des VLAN dans cet emplacement sont impactés, sans aucun recours possible. Nous vous encourageons à établir votre présence dans un autre centre de données, et à avoir recours à l'option [Spanning VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Si vos besoins en matière d'emplacement sont flexibles, il est préférable d'utiliser l'option d'emplacement la moins spécifique possible lorsque vous commandez des VLAN. De plus, des VLAN d'un emplacement précédent peuvent se libérer ultérieurement.


## Annuler des VLAN Premium
{:#canceling-premium-vlans}

Lorsque vous êtes prêt à supprimer un VLAN Premium, localisez le réseau dans la liste associée à votre compte (voir Gestion de réseaux locaux virtuels ci-dessus) et cliquez sur le symbole "X" en regard de l'entrée pour déclencher le processus d'annulation. 

Les VLAN Premium ne peuvent pas être annulés s'ils sont utilisés par d'autres produits. Les situations ci-dessous empêchent toute annulation :

  * Serveurs hébergés directement sur le VLAN (par opposition aux VLAN reliés).
  * Sous-réseaux secondaires routés vers le VLAN ou une adresse IP sur le VLAN.
  * Pare-feux s'exécutant sur l'ensemble du VLAN. Ceci exclut les pare-feux matériels non-dédiés, par exemple.
  * Association à un groupe de mise à l'échelle automatique.
  * Liaison aux serveurs (cette situation devrait changer prochainement).

De plus, certains produits et fonctionnalités **n'empêchent pas l'annulation** d'un VLAN, mais seront affectés par sa suppression. Par exemple :

  * La protection assurée par un dispositif de routeur virtuel. L'association au VLAN sera annulée, qu'elle soit ignorée ou non.

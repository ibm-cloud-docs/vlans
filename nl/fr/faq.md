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

# Foire aux questions
{:#vlans-faqs}


## Puis-je déplacer une unité existante vers un nouveau réseau local virtuel ?
{: faq}

Les unités existantes peuvent être déplacées vers d'autres réseaux locaux virtuels à condition qu'une demande de transfert soit émise. Les réseaux locaux virtuels étant associés à un routeur, et les connexions à chacun de ces routeurs étant fonction de l'emplacement physique de l'unité, il se peut que le transfert de certains VLAN impose une réinstallation physique. Cela est toujours le cas lorsque le nouveau VLAN se trouve dans un autre centre de données, mais cela peut également s'avérer nécessaire lorsqu'une unité est transférée vers un autre VLAN du même centre de données. Ce type de transfert implique l'interruption de connectivité du réseau ainsi que la modification de l'adresse IP de l'unité lorsque la connexion est déplacée vers le nouveau réseau local virtuel. Dans le cadre d'un transfert d'unité vers un nouveau VLAN, un temps d'arrêt suffisant doit être planifié, car la machine est hors ligne pendant toute la durée du transfert.


## Est-il possible de spécifier le VLAN que je souhaite utiliser avec mon unité au moment de la commande ?
{: faq}

Oui, vous pouvez indiquer un VLAN spécifique lors du processus de commande. Lorsque vous commandez une unité, cette option est disponible à la fin du formulaire de commande. Un réseau VLAN privé est sélectionné, suivi d'un réseau VLAN public. Notez également qu'un sélecteur de sous-réseau est affiché pour chaque VLAN (option **facultative**). Ne sélectionnez un sous-réseau que si vous avez une bonne raison de le faire, car sélectionner un sous-réseau qui ne dispose pas d'adresses IP disponibles peut avoir des conséquences négatives sur le fonctionnement de l'unité (voir la rubrique [FAQ sur les sous-réseaux](/docs/infrastructure/subnets?topic=subnets-subnets-faq) pour plus d'informations).

Il est important de noter que le VLAN sélectionné doit se trouver dans le même centre de données que l'unité. Nous ne pouvons pas affecter une unité à un VLAN qui se trouve dans un autre centre de données.


## Combien d'unités puis-je affecter à un seul réseau local virtuel ?
{: faq}

Actuellement, il n'y a pas de limite au nombre d'unités pouvant être associées à un même réseau local virtuel. Toutefois, lorsqu'un pare-feu matériel est associé à un VLAN, les règles du pare-feu peuvent imposer une limite au nombre d'unités hébergées sur le VLAN.


## Quels sont les types d'unités affectées à un réseau local virtuel ?
{: faq}

N'importe quelle unité dotée d'une connexion réseau peut être associée à un réseau local virtuel. Les serveurs dédiés disposant à la fois d'une connexion réseau publique et privée, vous verrez des unités être affectées à la fois à des VLAN publics et privés.

## Comment relier des réseaux VLAN à mes serveurs ?
{: faq}

Les réseaux virtuels locaux ne peuvent être reliés à des serveurs bare metal qu'au moyen de l'API. Aucune interface de portail n'est disponible pour cette activité. Pour plus d'informations sur la gestion des VLAN en tant que jonctions, consultez les liens ci-dessous.
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks
* https://softlayer.github.io/reference/services/SoftLayer_Network_Component/removeNetworkVlanTrunks

## Lors d'une commande de VLAN, que faut-il entendre par "Aucun VLAN n'est disponible" ?
{: faq}

Voir [Remarque relative à la capacité](/docs/infrastructure/vlans?topic=vlans-getting-started-with-vlans#a-note-about-capacity).


## Pourquoi mes unités ne peuvent-elles pas communiquer entre elles sur le même VLAN privé ?
{: faq}

Si chaque serveur se trouve sur un sous-réseau différent, par défaut, ils ne peuvent pas communiquer via les adresses IP. Techniquement, vos serveurs peuvent communiquer à l'aide des méthodes Couche 2 du modèle OSI car ils résident sur le même VLAN (conception de niveau couche 2). Pour que les communications par protocole IP aboutissent, vous pouvez soit ajouter une route au sous-réseau que vous tentez de joindre sur chaque serveur (la route sera différente sur chaque serveur), soit activer le [Spanning VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Notez que la fonctionnalité de [Spanning VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) peut avoir des répercussions. Par conséquent, examinez attentivement ses spécificités avant de l'activer.


## Quelles sont les options dont je dispose si je veux que les unités qui résident sur différents sous-réseaux privés d'un même VLAN communiquent entre elles par défaut, sans activer le Spanning VLAN ?
{: faq}

Nous savons que la gestion des routes sur les serveurs peut se révéler difficile sachant qu'{{site.data.keyword.cloud}} affecte et supprime automatiquement les sous-réseaux principaux en fonction des besoins. Nous savons également que le [Spanning VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning) n'est pas toujours une possibilité. Si votre déploiement est relativement important et que son exécution est entravée par ce comportement, vous pouvez demander un sous-réseau principal sur un [VLAN Premium](/docs/infrastructure/vlans?topic=vlans-about-vlans#premium-vlans) uniquement, par souci de flexibilité. Des frais variables vous seront facturés pour ce sous-réseau, en fonction de la demande. Nous nous réservons le droit d'accepter ou de refuser ces demandes, au cas par cas (chaque demande étant traitée indépendamment du type de compte). Suivez les instructions ci-dessous pour demander un sous-réseau principal de taille spéciale :

  1. Ouvrez la [console IBM Cloud ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/){: new_window} et connectez-vous à votre compte.
  1. Dans le menu, sélectionnez **Infrastructure classique**.  
  1. Dans le menu de navigation Infrastructure classique, sélectionnez **Réseau > Gestion IP > VLAN**.
  1. Commandez un VLAN Premium, si besoin. Voir [Commander des VLAN Premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans).
  1. Ouvrez un ticket en accédant à l'option de menu **Support > Ajouter un ticket**.
    - Objet : "Question réseau privé" ou "Question réseau public"
    - Titre : "Demande réseau principal étendu"
    - Détails : Indiquez le VLAN Premium sur lequel vous souhaitez installer le sous-réseau en utilisant la notation datacenter.router.vlan (par exemple, ams03.bcr01.1234). Précisez ensuite la taille de sous-réseau souhaitée en utilisant la notation CIDR (par exemple, /25). Indiquez le nombre de serveurs que vous envisagez d'acheter et sur quelle durée. Enfin, expliquez en quoi votre environnement peut être impacté en l'absence d'un tel sous-réseau. Soyez le plus explicite possible, car cette explication nous permet d'évaluer les améliorations à apporter à notre plateforme. Inutile de fournir des spécifications supplémentaires, car aucune autre propriété du sous-réseau ne sera prise en considération.

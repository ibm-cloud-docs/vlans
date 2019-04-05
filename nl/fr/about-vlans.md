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

# A propos des VLAN
{:#about-vlans}

Les réseaux locaux virtuels (VLAN) occupent une place centrale dans l'acheminement du trafic vers vos ressources. Vous pouvez ne jamais avoir besoin d'interagir directement avec des réseaux locaux virtuels, car ceux-ci sont gérés automatiquement : ils sont affectés et retirés en fonction des besoins. 

Un VLAN est un concept réseau. Il vous permet de créer des domaines de diffusion au niveau de la couche 2 du [Modèle OSI ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://en.wikipedia.org/wiki/OSI_model), à savoir la _couche liaison de données_. Les VLAN fournissent une méthode d'identification des paquets et permettent à plusieurs charges de travail de coexister sur le même équipement physique. Pour en savoir plus sur les réseaux locaux virtuels, voir [cet article ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://en.wikipedia.org/wiki/Virtual_LAN).

## Types de VLAN
{:#types-of-vlans}

Il existe deux types distincts de VLAN dans {{site.data.keyword.cloud}} : **Automatique** et **Premium**. Chacun joue un rôle différent, et selon vos besoins, il est essentiel d'en connaître les différences.

### VLAN automatiques
{:#automatic-vlans}

Les VLAN automatiques sont gérés directement par {{site.data.keyword.cloud}}. Ils sont affectés et retirés en fonction des besoins des autres produits que vous commandez. En règle générale, vous disposez d'un VLAN automatique par routeur. Les VLAN automatiques sont associés aux serveurs qui sont commandés sans spécifier de VLAN particulier. Il n'est pas possible de commander ou d'annuler des VLAN automatiques, car ceux-ci existent sur votre compte uniquement lorsque nos systèmes détectent qu'ils sont nécessaires, et les suppriment lorsqu'ils ne sont plus nécessaires.

### VLAN Premium
{:#about-premium-vlans}

Les VLAN Premium s'obtiennent en commandant un réseau local virtuel. Pour savoir comment faire, reportez-vous à la rubrique [Commander des VLAN Premium](/docs/infrastructure/vlans?topic=vlans-ordering-premium-vlans). Les réseaux locaux virtuels Premium restent sur votre compte tant qu'ils ne sont pas explicitement annulés. Vous pouvez commander autant de VLAN Premium que vous le souhaitez, sous réserve des limites de capacité. Si aucun réseau n'est disponible, recherchez des VLAN dans un autre pod ou centre de données.

L'une des particularités des réseaux locaux virtuels Premium est qu'ils ne sont pas sélectionnés automatiquement pour satisfaire une commande de serveur. Les VLAN Premium doivent être explicitement sélectionnés au cours du processus de commande du serveur afin que des serveurs résident sur eux. Pour plus d'informations sur la sélection des VLAN, veuillez consulter la [FAQ](/docs/infrastructure/vlans?topic=vlans-faqs#is-there-a-way-to-specify-which-vlan-i-want-to-use-for-my-device-when-i-order-it-).


## Identification des VLAN
{:#vlan-identification}

Les réseaux locaux virtuels (VLAN) résident sur les routeurs des centres de données IBM Cloud. Chaque VLAN est identifié par une combinaison numéro, routeur, emplacement de centre de données, unique. Par exemple, un réseau `VLAN 829` public, situé sur le routeur `fcr02` du centre de données `SJC01` sera identifié par le code `sjc01.fcr02.829`. Un réseau VLAN 2234 privé, situé sur le routeur `bcr01` du centre de données `AMS01` sera identifié par le code `ams01.bcr01.2234`.


## VLAN et sous-réseaux
{:#vlans-subnets}

Les réseaux locaux virtuels peuvent contenir un ou plusieurs sous-réseaux. A l'instar des VLAN, certains sous-réseaux sont automatiquement ajoutés et retirés, selon les besoins en adresses IP de vos unités. Vous trouverez de plus amples informations sur les types de sous-réseaux disponibles et leur mode de fonctionnement dans la section [Sous-réseaux et adresses IP](/docs/infrastructure/subnets?topic=subnets-getting-started-subnets-ips).


## Communication avec un VLAN
{:#communication-within-vlans}

Toutes les ressources situées sur un réseau local virtuel peuvent en théorie communiquer entre elles, mais cela ne veut pas dire qu'elles le font par défaut. Il est important de se rappeler que les VLAN appartiennent à la couche 2 du modèle OSI, tandis que les sous-réseaux/IP appartiennent à la couche 3. La communication s'effectue différemment sur chaque couche. Les ressources situées sur des VLAN différents, publics ou privés, ne peuvent pas communiquer les unes avec les autres via les mécanismes de la couche 2.

### Communication au sein d'un VLAN sur le réseau public
{:#communication-within-vlans-public}

Il n'existe pas de restrictions inhérentes à la communication entre les ressources d'un réseau public, qu'elles soient situées sur un ou plusieurs VLAN de l'infrastructure réseau public d'{{site.data.keyword.cloud}} ou sur Internet. Des restrictions peuvent être ajoutées en introduisant un dispositif de passerelle ou un pare-feu.

### Communication au sein d'un VLAN sur le réseau privé
{:#communication-within-vlans-private}

Par défaut, seuls les appareils installés sur le même sous-réseau peuvent communiquer entre eux, même si plusieurs sous-réseaux se trouvent dans le même réseau local virtuel. Toutefois, il est possible d'établir une communication avec d'autres sous-réseaux d'un même VLAN à condition que les instances possèdent des entrées de route pour les sous-réseaux supplémentaires sur le VLAN. La gestion des entrées de route sur tous les noeuds de traitement ayant besoin de dialoguer sur les sous-réseaux privés peut se révéler très complexe. Pour connaître les situations dans lesquelles une communication par défaut est requise entre toutes les instances d'un même VLAN, voir [Spanning VLAN](/docs/infrastructure/vlans?topic=vlans-vlan-spanning). Notez que cette fonctionnalité a d'importantes répercussions et doit être soigneusement examinée avant d'être activée.

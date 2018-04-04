---
copyright:
  years: 1994, 2017
lastupdated: "2017-10-20"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Initiation aux réseaux locaux virtuels

Un VLAN est un réseau local virtuel, qui est créé pour permettre à des clients de séparer des parties d'un réseau en plus petits sous-réseaux. Un VLAN fonctionne comme un conteneur au sein duquel les connexions et les adresses IP d'un client unique peuvent rester distinctes des autres clients. Les réseaux locaux virtuels assurent une meilleure sécurité et un meilleur isolement de certains problèmes. Sur notre réseau {{site.data.keyword.BluSoftlayer_notm}}, les VLAN offrent la possibilité de partitionner vos unités et sous-réseaux. 

Vous pouvez gérer les réseaux locaux virtuels depuis l'écran VLAN :

1. Depuis votre navigateur, ouvrez le [Portail client ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){: new_window} et connectez-vous à votre compte.
2. Dans l'arborescence du portail client, sélectionnez **Réseau > Gestion IP > VLAN**.

L'écran VLAN affiche des informations sur vos réseaux locaux virtuels, et permet d'accéder à chaque VLAN, de même que les unités ou sous-réseaux associés. En tant que service ajouté, les clients peuvent activer l'option Spanning VLAN qui connecte tous les VLAN de réseau privé sur un compte, ce qui permet aux unités situées sur des VLAN distincts de communiquer entre elles. 

## Identification de VLAN

Les VLAN sont utilisés sur les routeurs de nos centres de données. Chaque VLAN est identifié par un numéro, routeur et emplacement de centre de données uniques. Par exemple, le réseau `VLAN 829`, qui est installé sur le routeur `fcr02` du centre de données `SJC01`, est identifié par nos systèmes sous la forme `829 fcr02.sjc01`.

## Spanning VLAN 

La fonction Spanning VLAN est un paramètre de compte qui permet au trafic de circuler sur les réseaux locaux virtuels privés qui appartiennent à un même compte. En raison de la nature privée du réseau, peu de trafic est autorisé sur les réseaux locaux virtuels privés d'un compte. En règle générale, les VLAN protègent les unités contre le trafic réseau sur les autres comptes clients. Les VLAN privés vont encore un peu plus loin en matière de protection en limitant le trafic sur le VLAN aux unités qui se trouvent sur ce VLAN. Par conséquent, les unités qui sont situées sur deux VLAN privés différents n'échangent aucun trafic. Lorsque vous activez la fonction [Spanning VLAN](vlan-spanning.html), cette restriction est levée afin que les unités qui se trouvent sur les VLAN privés d'un même compte puissent communiquer entre elles.

### Dans quels cas dois-je activer la fonction Spanning VLAN sur mon compte ?

La fonction Spanning VLAN doit être activée dès lors que les besoins métier s'en font ressentir. Par exemple, si les serveurs hébergés sur plusieurs sous-réseaux privés ont besoin de communiquer, vous pouvez activer la fonction Spanning VLAN. La communication entre les VLAN ne dépend pas de l'emplacement physique du réseau local virtuel. Par exemple, les VLAN qui se trouvent dans le même centre de données restent totalement séparés les uns des autres. Lorsque les unités résident dans plusieurs VLAN, chacune d'elle possédant son propre sous-réseau, la fonction Spanning VLAN doit être activée pour permettre aux unités de communiquer.

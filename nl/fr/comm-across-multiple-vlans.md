---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-29"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Autoriser les serveurs à communiquer par le réseau privé sur plusieurs VLAN

**Pour les interconnexions entre serveurs**

 * Notre réseau privé est votre interconnexion. Lorsque vous achetez un premier serveur, un VLAN privé est créé pour votre compte, avec 64 adresses IP privées.
 * Si vous achetez ensuite d'autres serveurs, ils seront installés sur le même VLAN pour pouvoir communiquer entre eux via le réseau privé.
 * Si vous envisagez d'acquérir plus de 64 serveurs, le réseau local virtuel VLAN augmentera automatiquement en fonction de vos besoins. Il est inutile d'ouvrir un ticket de demande de service.
 * Nous ne pouvons pas toujours garantir que vos serveurs seront placés derrière les mêmes routeurs. En outre, si vous possédez des serveurs dans plusieurs emplacements, vous devrez activer l'option Private Network Spanning à partir du portail.

Ces paramètres sont accessibles depuis le [Portail client ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/) en sélectionnant **Réseau -> Gestion IP -> VLAN + Span (onglet)**.

Le système vous redirigera vers un nouvel écran dans lequel vous pourrez sélectionner **Oui**, puis l'option de **mise à jour du paramètre de la plage du VLAN** afin de terminer le processus de configuration.

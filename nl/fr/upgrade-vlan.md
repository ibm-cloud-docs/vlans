---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Mise à niveau d'un réseau local virtuel automatique
{:#upgrading-automatic-vlan}

Si vous avez articulé votre solution autour d'un VLAN automatique et que vous décidez ultérieurement de bénéficier des avantages d'un VLAN Premium, vous pouvez mettre à niveau votre réseau. Cette opération sera irréversible. Le réseau local virtuel devient un VLAN Premium et reste sur votre compte jusqu'à son annulation, après quoi il sera récupéré.

La mise à niveau des VLAN n'est pas toujours possible. Les limites de capacité s'appliquent.

A l'heure actuelle, la mise à niveau est disponible uniquement via l'API. Deux méthodes sont disponibles :

  1. Passer une commande en utilisant `SoftLayer_Product_Order.placeOrder`.
  2. Utiliser l'interface de raccourci `SoftLayer_Network_Vlan.upgrade`.

## Passer une commande
{:#place-vlan-order}

  1. Effectuez les mêmes étapes de commande que celles utilisées pour un VLAN Premium ; en indiquant spécifiquement le package correct et le prix.
  1. Supprimez les propriétés `location` et `routerId` requises lors de la commande d'un nouveau VLAN Premium.
  1. Ajoutez la propriété `id` et renseignez la valeur `SoftLayer_Network_Vlan.id` du VLAN à mettre à niveau.

## Interface de raccourci
{:#vlan-shortcut-interface}

Exécutez l'opération [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) sur un VLAN existant en initialisant l'appel avec la valeur `SoftLayer_Network_Vlan.id` du VLAN à mettre à niveau. Cela permet de localiser les informations de prix et de package appropriées pour le VLAN et de passer la commande nécessaire à la mise à niveau. Ainsi, les commandes de mise à niveau de VLAN seront passées uniquement si votre compte est admissible à l'approbation de commande automatique.

Pour plus d'informations, reportez-vous à la documentation de l'API [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/).

## Etapes suivantes
{:#upgrade-vlan-what-happens-next}

Le réseau local virtuel passe à Premium peu après la validation de la commande.

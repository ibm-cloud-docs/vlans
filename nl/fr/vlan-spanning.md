---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-27"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Activer ou désactiver la fonction Spanning VLAN

Parfois, plusieurs VLAN privés peuvent exister sur un même compte client. Toutefois, les unités réseau ne peuvent pas communiquer entre elles sur le réseau privé si elles n'appartiennent pas au même VLAN. La fonction Spanning VLAN permet à toutes les unités d'un même compte de communiquer les unes avec les autres par le biais du réseau privé, indépendamment du VLAN qui leur est affecté. 

Le service Spanning VLAN s'applique à toutes les unités d'un compte, autrement dit, il n'est pas possible de l'appliquer à des VLAN ou unités spécifiques. Vous pouvez activer ou désactiver la fonction selon vos besoins, sachant qu'il faut en moyenne 15 minutes pour que la modification soit prise en compte. Suivez les étapes ci-dessous pour activer ou désactiver la fonction Spanning VLAN sur un compte.


1. Depuis votre navigateur, ouvrez le [Portail client ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://control.softlayer.com/){: new_window} et connectez-vous à votre compte.
2. Dans l'arborescence du portail client, sélectionnez **Réseau > Gestion IP > VLAN**.
3. Sélectionnez l'onglet **Span** pour accéder à la section Spanning VLAN.
4. Sélectionnez le bouton radio **Activé**si vous souhaitez activer la fonction Spanning VLAN. Sélectionnez **Désactivé** dans le cas contraire.

## Etapes suivantes

Lorsque vous modifiez le paramètre d'activation/de désactivation de la fonction Spanning VLAN, le processus peut prendre jusqu'à 15 minutes. La confirmation des changements apparaît sous l'onglet Span. Si vous avez activé la fonction Spanning VLAN, les unités peuvent communiquer entre elles sur les réseaux locaux virtuels à l'aide du réseau privé. Si vous l'avez désactivée, les unités peuvent se connecter les unes aux autres uniquement si elles résident sur le même réseau local virtuel. La communication entre les VLAN n'est alors plus activée. Vous pouvez modifier le paramètre Spanning VLAN à tout moment en répétant les étapes ci-dessus. **Remarque :** Si vous modifiez plusieurs fois en peu de temps le paramètre de la fonction Spanning VLAN, son application pourra être retardée.

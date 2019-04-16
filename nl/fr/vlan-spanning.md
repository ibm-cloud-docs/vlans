---

copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-28"

keywords: VLAN Spanning VLAN, Default values, VLAN Spanning

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}


# Spanning VLAN
{: #vlan-spanning}

Le Spanning VLAN permet à toutes les unités d'un même compte de communiquer les unes avec les autres par le biais du réseau privé, indépendamment du VLAN affecté aux unités.
{: #shortdesc}

## Présentation du Spanning VLAN
{: #understanding-vlan-spanning}


Dans {{site.data.keyword.Bluemix}}, le Spanning VLAN peut être utilisé pour différentes raisons et a une incidence sur la communication de l'unité. Pour en savoir plus sur le fonctionnement de base du Spanning VLAN avant de commencer, lisez les informations ci-dessous.
{: shortdesc}

### Fonctionnement du Spanning VLAN
{: #how-vlan-spanning-works}

En activant la fonction de Spanning VLAN, l'ensemble du trafic routé peut circuler entre tous les sous-réseaux privés, sur tous les VLAN privés associés à votre compte. Ceci répond aux besoins métier qui nécessitent une communication globale du trafic routé. Par exemple, vous pouvez activer le Spanning VLAN si les unités hébergées sur plusieurs sous-réseaux privés ont besoin de communiquer et ce, qu'elles soient sur le même réseau local virtuel ou non.

Lorsque la fonction de spanning est activée, elle s'exécute sur l'ensemble du compte. Vous ne pouvez pas exclure de sous-réseaux, de VLAN ni d'unités. Si vous vous appuyez uniquement sur des sous-réseaux privés pour séparer les serveurs en rôles ou tiers, l'activation du Spanning VLAN annule la ségrégation.
{:note}

### Valeurs par défaut
{: #vlan-spanning-default-values}

Par défaut, le Spanning VLAN est désactivé. Les unités situées sur deux sous-réseaux privés différents, dans le cadre d'un seul VLAN ou non, ne seront pas en mesure d'envoyer et de recevoir le trafic IP les unes vers les autres.

### Services ayant généralement besoin du Spanning VLAN
{: #vlan-spanning-services}

Des tutoriels spécifiques sont mis à votre disposition afin de vous aider à configurer le Spanning VLAN en fonction de votre situation. Voir les liens [Autres ressources](/docs/infrastructure/vlans?topic=vlans-other-resources-vlan-spanning).


## Gestion du Spanning VLAN
{: #manage-vlan-spanning}

Vous pouvez activer ou désactiver le Spanning VLAN sur votre compte.
{: shortdesc}

Pour mettre à jour les paramètres de votre compte, procédez comme suit :

  1. Dans votre navigateur, ouvrez la console [{{site.data.keyword.Bluemix_notm}} ![Icône de lien externe](../../icons/launch-glyph.svg "Icône de lien externe")](https://{DomainName}/){: new_window} et connectez-vous à votre compte.
  2. Dans le menu, sélectionnez **Infrastructure**. Le portail client s'affiche.
  3. Dans l'arborescence du portail client, sélectionnez **Réseau > Gestion IP > VLAN**.
  4. Sélectionnez l'onglet **Span** pour accéder à la section Spanning VLAN.
  5. Sélectionnez le bouton d'option **Activé** ou **Désactivé** conformément à vos besoins.

L'activation/la désactivation du Spanning VLAN dans un court laps de temps peut entraîner des retards.
{:note}

La demande de mise à jour peut nécessiter jusqu'à 15 minutes. Une confirmation de la modification apparaît à l'écran. Vous pouvez mettre à jour vos paramètres Spanning VLAN à tout moment, en répétant les étapes ci-dessus.

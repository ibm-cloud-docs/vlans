---
copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-27"

keywords: IBM Cloud Kubernetes Service, IBM Cloud infrastructure account, private network

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}

# Autres ressources pour le Spanning VLAN
{:#other-resources-vlan-spanning}

Lorsque vous travaillez avec [{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html), vous devez régulièrement activer le Spanning VLAN. Si vous avez plusieurs réseaux locaux virtuels pour un cluster, plusieurs sous-réseaux sur le même réseau local virtuel ou un cluster multizone, vous devez activer le Spanning VLAN pour votre compte d'infrastructure {{site.data.keyword.Bluemix_notm}} afin que vos noeuds worker puissent communiquer entre eux sur le réseau privé. Si vous ne disposez pas des droits requis pour effectuer cette action, demandez au propriétaire du compte de l'activer. Si vous n'êtes pas sûr de savoir si le Spanning VLAN est activé ou non, exécutez la commande `ibmcloud ks vlan-spanning-get` pour consulter le statut de votre compte.

Si vous utilisez {{site.data.keyword.BluDirectLink}}, vous devez exécutez une [Fonction de routeur virtuel (VRF)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf) à la place. Pour activer une fonction de routeur virtuel, contactez le représentant de compte de votre infrastructure {{site.data.keyword.Bluemix_notm}}.

Pour obtenir de l'aide sur certaines tâches spécifiques relatives aux VLAN, consultez les ressources ci-dessous. 

* [Premium VLANs](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [Tutorial on setting up classic VLAN spanning using VRAs](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [For Kubernetes service, configuring edge nodes with multiple VLANs](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [IBM Cloud CLI commands for VLANs](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Route multiple VLANs over the same network interface using Juniper vSRX](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [Configuring subnets for Kubernetes clusters](/docs/containers?topic=containers-subnets#vlan-spanning)
* [Overview of IBM Cloud Networking, VLAN spanning for VMware solutions](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


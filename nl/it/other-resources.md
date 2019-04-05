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

# Altre risorse per lo spanning della VLAN
{:#other-resources-vlan-spanning}

Quando lavori con [{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html), spesso devi abilitare lo spanning della VLAN. Se hai più VLAN per un cluster, più sottoreti sulla stessa VLAN o un cluster multizona, devi abilitare lo spanning della VLAN per il tuo account dell'infrastruttura {{site.data.keyword.Bluemix_notm}} in modo che i tuoi nodi di lavoro possano comunicare tra loro sulla rete privata. Se non disponi dell'accesso corretto per eseguire questa azione, puoi richiedere al proprietario dell'account di abilitarlo. Se non sei sicuro che lo spanning della VLAN sia abilitato, puoi eseguire `ibmcloud ks vlan-spanning-get` per vedere lo stato del tuo account.

Se stai utilizzando {{site.data.keyword.BluDirectLink}}, devi utilizzare invece una [VRF (Virtual Router Function)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf). Per abilitare la VRF, contatta il tuo rappresentante dell'account dell'infrastruttura {{site.data.keyword.Bluemix_notm}}.

Per assistenza con attività specifiche che coinvolgono le VLAN, fai riferimento alle seguenti risorse. 

* [VLAN premium](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [Esercitazione sulla configurazione dello spanning della VLAN classico utilizzando i VRA](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [Per il servizio Kubernetes, configurazione dei nodi edge con più VLAN](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [Comandi della CLI IBM Cloud per le VLAN](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Instradamento di più VLAN sulla stessa interfaccia di rete utilizzando Juniper vSRX](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [Configurazione di sottoreti per i cluster Kubernetes](/docs/containers?topic=containers-subnets#vlan-spanning)
* [Panoramica della rete IBM Cloud e dello spanning della VLAN per le soluzioni VMware](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


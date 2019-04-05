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

# Weitere Ressourcen für VLAN-Spanning
{:#other-resources-vlan-spanning}

Wenn Sie mit [{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html) arbeiten, müssen Sie häufig das VLAN-Spanning aktivieren. Falls Sie über mehrere VLANs für einen Cluster, mehrere Teilnetze für dasselbe VLAN oder einen Mehrzonencluster verfügen, müssen Sie das VLAN-Spanning für das {{site.data.keyword.Bluemix_notm}}-Infrastrukturkonto aktivieren, damit die Workerknoten im privaten Netz miteinander kommunizieren können. Wenn Sie nicht über die korrekte Zugriffsberechtigung zur Ausführung dieser Aktion verfügen, können Sie den Kontoeigentümer auffordern, diese zu aktivieren. Wenn Sie nicht sicher sind, ob das VLAN-Spanning aktiviert ist, können Sie `ibmcloud ks vlan-spanning-get` ausführen, um den Kontostatus anzuzeigen.

Wenn Sie {{site.data.keyword.BluDirectLink}} verwenden, müssen Sie eine [ VRF-Funktion (Virtual Router Function)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf) verwenden. Wenn Sie VRF aktivieren möchten, wenden Sie sich an den Ansprechpartner für Ihr {{site.data.keyword.Bluemix_notm}}-Infrastrukturkonto.

Hilfe zu bestimmten Tasks mit VLANs finden Sie in den folgenden Ressourcen. 

* [Premium-VLANs](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [Lernprogramm zum Konfigurieren eines klassischen VLAN-Spanning mit VRAs](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [Edge-Knoten mit mehreren VLANs für Kubernetes-Service konfigurieren](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [Befehle der IBM Cloud-Befehlszeilenschnittstelle für VLANs](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Mehrere VLANs über dieselbe Netzschnittstelle mit Juniper vSRX weiterleiten](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [Teilnetze für Kubernetes-Cluster konfigurieren](/docs/containers?topic=containers-subnets#vlan-spanning)
* [Übersicht über IBM Cloud-Netzbetrieb, VLAN-Spanning für VMware-Lösungen](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


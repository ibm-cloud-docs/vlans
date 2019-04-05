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

# Outros recursos para a ampliação de VLAN
{:#other-resources-vlan-spanning}

Ao trabalhar com o [{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html), é frequentemente necessário ativar a ampliação de VLAN. Quando há diversas VLANs para um cluster, diversas sub-redes na mesma VLAN ou um cluster de diversas zonas, deve-se ativar a ampliação de VLAN para a conta de infraestrutura do {{site.data.keyword.Bluemix_notm}}, para que os nós do trabalhador possam se comunicar uns com os outros na rede privada. Caso você não tenha o acesso correto para executar essa ação, será possível solicitar que o proprietário da conta o ative. Caso não tenha certeza se a ampliação de VLAN está ativada, será possível executar o `ibmcloud ks vlan-spanning-get` para ver o status de sua conta.

Ao usar o {{site.data.keyword.BluDirectLink}}, deve-se usar uma [Função de Roteador Virtual (VRF)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf). Para ativar a VRF, entre em contato com o representante de sua conta de infraestrutura do {{site.data.keyword.Bluemix_notm}}.

Para obter ajuda com tarefas específicas que envolvem VLANs, consulte os seguintes recursos. 

* [VLANs Premium](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [Tutorial sobre como configurar a ampliação de VLAN clássica usando VRAs](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [Para o serviço Kubernetes, configurando nós de borda com diversas VLANs](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [Comandos da CLI do IBM Cloud para VLANs](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Encaminhar diversas VLANs pela mesma interface de rede usando o Juniper vSRX](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [Configurando sub-redes para clusters do Kubernetes](/docs/containers?topic=containers-subnets#vlan-spanning)
* [Visão geral do IBM Cloud Networking e da ampliação de VLAN para soluções VMware](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


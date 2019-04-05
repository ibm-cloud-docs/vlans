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

# Otros recursos para la expansión de VLAN
{:#other-resources-vlan-spanning}

Al trabajar con [{{site.data.keyword.containerlong_notm}}](https://{DomainName}/docs/containers/container_index.html), a menudo necesitará habilitar la expansión de VLAN. Si tiene varias VLAN para un clúster, varias subredes en la misma VLAN, o un clúster multizona, debe habilitar la expansión de VLAN para su cuenta de infraestructura de {{site.data.keyword.Bluemix_notm}} para que sus nodos trabajadores puedan comunicarse entre ellos en la red privada. Si no tiene el acceso correcto para realizar esta acción, puede solicitar que el propietario de la cuenta lo habilite. Si no está seguro de si está habilitada la expansión de VLAN, puede ejecutar `ibmcloud ks vlan-spanning-get` para ver el estado de su cuenta.

Si utiliza {{site.data.keyword.BluDirectLink}}, debe utilizar [Virtual Router Function (VRF)](https://{DomainName}/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf) en su lugar. Para habilitar VRF, póngase en contacto con su representante de cuenta de infraestructura de {{site.data.keyword.Bluemix_notm}}.

Para obtener ayuda para tareas específicas relacionadas con las VLAN, consulte los siguientes recursos. 

* [VLAN Premium](https://www.ibm.com/blogs/bluemix/2018/12/introducing-premium-vlans-are-you-compute-first-or-network-first/)
* [Guía de aprendizaje sobre cómo configurar la expansión de VLAN clásica utilizando VRA](/docs/tutorials?topic=solution-tutorials-vlan-spanning)
* [Para el servicio Kubernetes, configuración de nodos extremos con varias VLAN](/docs/containers?topic=containers-edge_nodes_multiple_vlans)
* [Mandato de CLI de IBM para las VLAN](/docs/cli/reference/ibmcloud?topic=cloud-cli-manage-classic-vlans)
* [Direccionar varias VLAN en la misma interfaz de red utilizando Juniper vSRX](/docs/infrastructure/vsrx?topic=vsrx-route-multiple-vlans-over-the-same-network-interface)
* [Configuración de subredes para clústeres de Kubernetes](/docs/containers?topic=containers-subnets#vlan-spanning)
* [Visión general de la red de IBM Cloud, expansión de VLAN para VMware Solutions](/docs/services/vmwaresolutions/archiref/vcsnsxt?topic=vmware-solutions-vcsnsxt-overview-ic4vnetwork#vcsnsxt-overview-ic4vnetwork-vlan-spanning)


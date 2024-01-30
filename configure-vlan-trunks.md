---

copyright:
  years: 2022
lastupdated: "2022-04-13"

keywords:

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# Configuring VLAN trunks
{: #configuring-vlan-trunks}

Servers can establish trunks with Automatic and Premium VLANs so that traffic can flow between devices using different VLANs than the ones chosen during provisioning.
{: shortdesc}

You can use VLAN trunks for many purposes, including, but not limited to:

- Segmenting guests into different VLANs by adding VLAN trunks to hypervisor hosts (such as ESXi, Hyper-V and Xen Server)
- Providing more direct access to external storage or other devices (commonly used when the host is behind a gateway device)

You can add and remove VLAN trunks to a server's interface. The VLAN and server for the VLAN trunk must reside in the same pod as the server whose network interface is being connected. VLANs and their trunks must also be in the same network because private VLANs can only be trunked to private interfaces and public VLANs can only be trunked to public interfaces.

You cannot establish VLAN trunks against management ports.
{: note}

## Learning about network interfaces
{: #about-network-interfaces}

Network component groups are multiple physical interfaces participating in a logical redundant connection. A device can have multiple network interfaces and network interface groups. When you establish a trunk to any member in the group, that VLAN trunk is replicated to all group members.

## Managing VLAN trunks using the UI
{: #ui-manage-trunks}
{: ui}

You can establish or remove VLAN trunks using the UI.

When you want to change multiple VLAN trunks with a bare metal server, consider using the bare metal server page that can affect multiple VLAN trunks at a time. For more information, see [bare metal VLAN trunks](/docs/bare-metal?topic=bare-metal-network-options#bare-metal-vlan-trunks).
{: tip}

### Creating VLAN trunks using the UI
{: #ui-create-vlan-trunks}

Create a VLAN trunk using the console by taking the following steps:

1. From your browser, open the [IBM Cloud console](/login) and log in to your account.
1. From the console, click the Navigation Menu icon ![Navigation Menu icon](../../icons/icon_hamburger.svg) and select **Classic Infrastructure**.
1. Select **Network > IP Management > VLANs**.
1. Select a VLAN by clicking on its fully qualified name in the list of VLANs.
1. Click **Attach trunk** in the **Devices with trunks** section.
1. Select a resource from the devices list in the panel that appears.
1. Click **Attach** to establish the trunk, or click **Cancel** to close the panel without adding the trunk.


Add VLANs as trunks to a network component. The VLANs given must be assigned to your account, and on the router to which this network component is connected. The native VLAN (`networkVlanId/networkVlan`) of the selected device cannot be added as a trunk.

You must manually configure your host's network with your added VLAN trunks before they can be used to pass traffic.
{: note}

### Removing VLAN trunks using the UI
{: #ui-remove-vlan-trunks}

Remove a VLAN trunk using the console by taking the following steps:

1. From your browser, open the [IBM Cloud console](/login) and log in to your account.
1. From the console, click the Navigation Menu icon ![Navigation Menu icon](../../icons/icon_hamburger.svg) and select **Classic Infrastructure**.
1. Select **Network > IP Management > VLANs**.
1. Select a VLAN by clicking on its fully qualified name in the list of VLANs.
1. Select **Remove** from the Actions menu ![Actions menu](/images/overflow.png) of the trunk you want to remove.
1. Click **Remove trunk** to remove the trunk, or click **Cancel** to close the panel without removing the trunk.

## Managing VLAN trunks using the API
{: #api-manage-trunks}
{: api}

You can create and remove VLAN trunks by using the API.

### Creating VLAN trunks using the API
{: #api-create-vlan-trunks}

For more information on creating VLAN trunks using the API, see [addNetworkVlanTrunks](https://sldn.softlayer.com/reference/services/SoftLayer_Network_Component/addNetworkVlanTrunks/){: external}

### Removing VLAN trunks using the API
{: #api-remove-vlan-trunks}

For more information on removing VLAN trunks using the API, see [clearNetworkVlanTrunks](https://sldn.softlayer.com/reference/services/SoftLayer_Network_Component/clearNetworkVlanTrunks/){: external}

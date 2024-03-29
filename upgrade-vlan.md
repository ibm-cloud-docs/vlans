---

copyright:
  years: 1994, 2019
lastupdated: "2022-05-12"

keywords: upgrade automatic vlan

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# Upgrading an automatic VLAN
{: #upgrading-automatic-vlan}
{: help}
{: support}

If you built a solution around an Automatic VLAN and later decide you want it to have the capabilities of a Premium VLAN, you can upgrade it. Upgrading is not reversible. The VLAN becomes a Premium VLAN and stays on your account until canceled, at which point it is reclaimed.
{: shortdesc}

Upgrading VLANs is not always possible. VLAN capacity limitations still apply.

For the moment, upgrading is only available via the API. Two methods are available to do so:

1. Place an order using `SoftLayer_Product_Order.placeOrder`.
2. Use the `SoftLayer_Network_Vlan.upgrade` shortcut interface.

## Placing an order
{: #place-vlan-order}

1. Construct an order similar to a typical Premium VLAN, with the correct package and pricing.
1. Remove the `location` and `routerId` properties that are required when you order a new Premium VLAN.
1. Add the `id` property, and populate it with the `SoftLayer_Network_Vlan.id` value of the Automatic VLAN to upgrade.

## Shortcut interface
{: #vlan-shortcut-interface}

Run the [SoftLayer_Network_Vlan.upgrade](https://sldn.softlayer.com/reference/services/SoftLayer_Network_Vlan/upgrade/){: external} operation against an existing Automatic VLAN by initializing the call with the `SoftLayer_Network_Vlan.id` value of the VLAN to upgrade. This operation locates the appropriate package and pricing information for the VLAN, and places the necessary order to perform the upgrade. Using this method, VLAN upgrade orders are placed only if your account qualifies for automatic order approval. See [SoftLayer_Network_Vlan.upgrade](https://sldn.softlayer.com/reference/services/SoftLayer_Network_Vlan/upgrade/){: external} in the API documentation for more details.

## What happens next
{: #upgrade-vlan-what-happens-next}

The Automatic VLAN is converted to a Premium VLAN shortly after a successful order is placed.

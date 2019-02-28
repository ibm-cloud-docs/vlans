---
copyright:
  years: 1994, 2018, 2019
lastupdated: "2019-02-27"

keywords: Automatic VLAN, capabilities of a Premium VLAN, upgrade shortcut interface

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Upgrading an Automatic VLAN
{:#upgrading-automatic-vlan}

If you built a solution around an Automatic VLAN and later decide you want it to have the capabilities of a Premium VLAN, you can upgrade it. Upgrading is not reversible. The VLAN becomes a Premium VLAN and remains on your account until canceled; at which point it will be reclaimed.

Upgrading VLANs is not always possible. VLAN capacity limitations still apply.

For the moment, upgrading is only available via the API. Two methods are available to do so:

  1. Place an order utilizing `SoftLayer_Product_Order.placeOrder`.
  2. Utilize the `SoftLayer_Network_Vlan.upgrade` shortcut interface.

## Placing an order
{:#place-vlan-order}

  1. Construct an order similar to a typical Premium VLAN; specifically with the correct package and pricing.
  1. Remove the `location` and `routerId` properties that are required when ordering a new Premium VLAN.
  1. Add the `id` property, and populate it with the `SoftLayer_Network_Vlan.id` value of the VLAN to upgrade.

## Shortcut interface
{:#vlan-shortcut-interface}

Execute the [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) operation against an existing VLAN by initializing the call with the `SoftLayer_Network_Vlan.id` value of the VLAN to upgrade. This locates the appropriate package and pricing information for the VLAN, and places the necessary order to perform the upgrade. Using this method, VLAN upgrade orders will only be placed if your account qualifies for automatic order approval.

See the API documentation for [SoftLayer_Network_Vlan.upgrade](https://softlayer.github.io/reference/services/SoftLayer_Network_Vlan/upgrade/) for more details.

## What Happens Next?
{:#upgrade-vlan-what-happens-next}

The VLAN is transitioned to a Premium VLAN shortly after a successful order is placed.

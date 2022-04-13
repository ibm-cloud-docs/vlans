---

copyright:
  years: 2021, 2022
lastupdated: "2022-04-08"

keywords:

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# Why can't I cancel the VLAN billing items?
{: #cannot-cancel-vlan}
{: troubleshoot}

You receive an error message when you attempt to cancel a VLAN.
{: shortdesc}

You attempt to cancel VLAN billing items by completing the steps in [Cancelling your billing items](/docs/billing-usage?topic=billing-usage-cancel-billing-items). However, an error message displays that contains the following text:
{: tsSymptoms}

`Unable to cancel VLAN`

This error message occurs when the VLAN is still associated with resources.
{: tsCauses}

Trunked VLANs prevent the cancellation, but you can self-manage this issue without contacting IBM Support.  

You must cancel the associated resources prior to attempting to cancel the associated VLANs. You can cancel VLANs that were ordered independently of a device when references to the VLAN do not remain. 
{: tsResolve}

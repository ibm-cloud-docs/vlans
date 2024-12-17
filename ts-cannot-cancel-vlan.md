---

copyright:
  years: 2021, 2024
lastupdated: "2024-12-17"

keywords:

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# Why can't I cancel the VLAN billing items?
{: #cannot-cancel-vlan}
{: troubleshoot}

You receive an error message when you attempt to cancel a VLAN.
{: shortdesc}

You attempt to cancel VLAN billing items. However, an error message displays that contains the following text:
{: tsSymptoms}

`Unable to cancel VLAN`

This error message occurs when the VLAN is still associated with resources.
{: tsCauses}

You must cancel the associated resources prior to attempting to cancel the associated VLANs. You can cancel premium VLANs when there are no references to the VLAN.
{: tsResolve}

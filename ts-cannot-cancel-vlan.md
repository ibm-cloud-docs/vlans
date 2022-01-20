---

copyright:
  years: 2021
lastupdated: "2021-12-27"

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

Trunked VLANs cannot be cancelled without assistance from Network Technical Support. Contact [Support](https://{DomainName}/unifiedsupport/supportcenter) for assistance.
{: note}

You must cancel the associated resources prior to attempting to cancel the associated VLANs. You can cancel VLANs that were ordered independently of a device when references to the VLAN do not remain. 
{: tsResolve}

References include devices on the VLAN and portable subnets that are ordered on the VLAN. There are two types of VLANs:

- Automatic VLANs, which are provided by the automated system when you order your first server in a data center. After you cancel the associated server, the VLAN is automatically reclaimed.
- Premium VLANs are separately ordered as explained in the Ordering premium VLANs documentation. You cannot adjust these VLANs after they are provisioned. Also, premium VLANs cannot be canceled if they are being used by other resources. For premium VLANs that are associated with a gateway appliance, you must first disassociate the VLAN before you cancel it. The disassociation occurs automatically if the gateway appliance is canceled. However, you can only cancel the VLAN after the gateway appliance cancellation process has completed. For more information, see [Canceling premium VLANs](/docs/vlans?topic=vlans-getting-started#canceling-premium-vlans).

1. Complete the following steps to determine which devices are associated with the applicable VLANs:
    - Log in to the [{{site.data.keyword.cloud_notm}} console](https://{DomainName}/).
    - Click the three parallel lines in the upper left corner of the console.
    - Select **Classic Infrastructure > Overview**.
    - Expand **Network** and select **IP Management > VLANs**.
    - Click the number in the **VLAN Number** column to obtain details about the associated devices and subnets. You must cancel the associated device before you can cancel the VLAN. 

2. Complete the following steps to cancel the device:
    - Click the three parallel lines in the upper left corner of the console.
    - Select **Classic Infrastructure > Device List**.
    - Click the three dots on the far right side of the row for the applicable device. 
    - Select **Cancel device**.

3. Complete the steps in [Canceling a VLAN](/docs/vlans?topic=vlans-cancel-vlan).

---

copyright:
  years: 1994, 2019
lastupdated: "2019-08-07"

keywords: cancel VLANs

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# Canceling a VLAN
{: #cancel-vlan}

VLANs ordered independently of a device can be canceled when no references to the VLAN remain.
{: shortdesc}

References include devices on the VLAN and portable subnets that are ordered on the VLAN.

For premium VLANs that are associated with a gateway appliance, you must first [disassociate](/docs/virtual-router-appliance?topic=gateway-appliance-managing-vlans-and-gateway-appliances#disassociate-a-vlan-from-a-gateway-appliance) the VLAN before you cancel it. The disassociation occurs automatically if the gateway appliance is canceled, but you can only cancel the VLAN after the gateway appliance cancellation has completed.
{: note}

Follow these steps to cancel a VLAN.

1. From your browser, open the [IBM Cloud console](https://{DomainName}/) and log in to your account.
1. In the menu, select **Classic Infrastructure**.
1. Select **Network > IP Management > VLANs**.
1. Choose the **Cancel** icon for the wanted VLAN.
1. Select the appropriate **Cancel** method based how you want to cancel the VLAN.

    Specific information on cancellation options is displayed next to each item.
    {: note}
    
1. Enter notes about the cancellation in the **Notes** text box.
1. Select **Continue** to proceed to the confirmation message, or select **Cancel** to cancel the action.
1. Review the **Terms of Service** accessible on the screen, and click the **Acknowledgement** checkbox.
1. Select **Cancel VLAN** to confirm the cancellation, or select **Close** to cancel the action and keep the VLAN active.

## What happens next
{: #cancel-vlan-what-happens-next}

The VLAN is canceled after you submit a cancellation request. VLANs are canceled either immediately, or on the billing anniversary date. If you choose to cancel the VLAN immediately, the VLAN is reclaimed as soon as possible. If you select cancellation on the billing anniversary date, the VLAN remains active until the billing anniversary date.

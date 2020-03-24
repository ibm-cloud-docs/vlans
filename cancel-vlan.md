---
copyright:
  years: 1994, 2019
lastupdated: "2019-08-07"

keywords: VLANs, different role, network concept

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:external: target="_blank" .external}
{:generic: data-hd-programlang="generic"}

# Canceling a VLAN
{:#cancel-vlan}

VLANs ordered independently of a device can be canceled when there are no references to the VLAN.  References include devices on the VLAN and portable subnets ordered on the VLAN.

Follow the steps in this article to cancel a VLAN.

1. From your browser, open the [IBM Cloud console](https://{DomainName}/){: new_window} and log into your account.
1. In the menu, select **Classic Infrastructure**.
1. Select **Network > IP Management > VLANs**.
1. Choose the **Cancel** icon for the wanted VLAN.
1. Select the appropriate **Cancel** radio box based on your preference of how the VLAN should be canceled.

      Specific information on cancellation options is displayed next to each radio button.
      {:note}
1. Enter notes regarding the cancellation in the **Notes** text box.
1. Select the **Continue** button to proceed to the confirmation pop-up box, or select the **Cancel** button to cancel the action.
1. Review the **Terms of Service** accessible on the screen, and click the **Acknowledgement** check box.
1. Select the **Cancel VLAN** button to confirm the cancellation, or select the **Close** button to cancel the action and keep the VLAN active.

## What happens next
{:#cancel-vlan-what-happens-next}

After submitting a cancellation request, the VLAN is canceled according to your selection: either immediately, or on the billing anniversary date. If you choose to cancel the VLAN immediately, the VLAN is reclaimed as soon as possible. If you select cancellation on the billing anniversary date, the VLAN remains active until the billing anniversary date.

---

copyright:
  years: 1994, 2022
lastupdated: "2022-12-16"

keywords: cancel VLANs

subcollection: vlans

---

{{site.data.keyword.attribute-definition-list}}

# Canceling a Premium VLAN
{: #cancel-vlan}

You can cancel your Premium VLANs when you no longer need them and when they are empty of native devices, or have devices which are all canceled. Trunked devices do not prevent cancelation.
{: shortdesc}

Follow these steps to cancel a Premium VLAN.

1. From your browser, open the [IBM Cloud console](/login) and log in to your account.
1. From the console, click the Navigation Menu icon ![Navigation Menu icon](../../icons/icon_hamburger.svg) and select **Classic Infrastructure**.
1. Select **Network > IP Management > VLANs**.
1. Select **Cancel VLAN** from the Actions menu ![Actions menu](/images/overflow.png) of the Premium VLAN that you want to cancel.
1. Select the appropriate **Cancel** method based on when you want to cancel the VLAN.

    Specific information on cancellation options is displayed next to each item.
    {: note}

1. Select **Confirm** to confirm the cancellation, or select **Close** to cancel the action and keep the VLAN active.


You can alternatively click **Actions > Cancel VLAN** on the **VLAN Details** page.
{: tip}

## What happens next
{: #cancel-vlan-what-happens-next}

Premium VLANs are canceled either immediately or on the billing anniversary date. If you choose to cancel the VLAN immediately, the VLAN is reclaimed as soon as possible. If you select cancellation on the billing anniversary date, the VLAN remains on your account and active until the billing anniversary date.

Any secondary subnets present on the VLAN will be unrouted as part of VLAN reclaim, and any trunks present on the VLAN will be automatically removed.

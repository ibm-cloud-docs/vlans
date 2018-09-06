---
copyright:
  years: 1994, 2017
lastupdated: "2018-08-24"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# VLAN Spanning
{: #vlan-spanning}

VLAN spanning enables all devices on an account to communicate with each other by means of the private network, regardless of the devices assigned VLAN.
{: #shortdesc}

## Understanding VLAN spanning
{: #understanding}


In {{site.data.keyword.Bluemix}}, VLAN spanning can be used for many different purposes and has an impact on device communication. To learn more about the basics of VLAN spanning before you get started, review the following questions and answers.
{: shortdesc}

### How does VLAN spanning work?

By enabling VLAN spanning, all of your routed traffic is able to travel between the VLANs and private subnets in your account. There are times that a business need might arise that requires the global communication of your routed traffic. For example: if devices that reside on more than one private subnet, or VLANS need to communicate, then VLAN spanning should be enabled.

**Note**: When spanning is enabled, it affects the entire account. You cannot specify VLANS or devices for which VLAN spanning is not applied.

### What is the default?

By default, VLAN spanning is disabled. Devices located on two different private VLANS or subnets within the same VLAN can not send IP traffic to each other.

### Are there any services that commonly require VLAN spanning?

When working with [{{site.data.keyword.containerlong_notm}}](/docs/containers/container_index.html), you frequently need to enable VLAN spanning. If you have multiple VLANs for a cluster, multiple subnets on the same VLAN, or a multizone cluster, you must enable VLAN spanning for your {{site.data.keyword.Bluemix_notm}} infrastructure account so your worker nodes can communicate with each other on the private network. If you do not have the correct access to perform this action, you can request that the account owner enable it. If you're unsure about whether VLAN spanning is enabled, you can run `ibmcloud ks vlan-spanning-get` to see your account status.

If you are using {{site.data.keyword.BluDirectLink}}, you must use a [Virtual Router Function (VRF)](/docs/infrastructure/direct-link/subnet-configuration.html#more-about-using-vrf) instead. To enable VRF, contact your {{site.data.keyword.Bluemix_notm}} infrastructure account representative.


## Managing VLAN spanning
{: #manage}

You can enable or disable VLAN spanning for your account.
{: shortdesc}

To update your account setting, follow these steps:

  1. From your browser, open the [{{site.data.keyword.Bluemix_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.bluemix.net/){: new_window} and log into your account.
  2. In the menu, select **Infrastructure**. The Customer Portal opens.
  3. In the Customer Portal navigation, select **Network > IP Management > VLANs**.
  4. Select the **Span** tab to access the VLAN Spanning section.
  5. Select the **On** or **Off** radio button as desired to enable or disable VLAN spanning respectively.

**Note**: Toggling VLAN Spanning within a short amount of time might result in delayed application.

The update request can take up to 15 minutes to process. A confirmation of the change displays on the screen. You can update your VLAN spanning settings at any time by repeating the previous steps.

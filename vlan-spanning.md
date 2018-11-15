---
copyright:
  years: 1994, 2017
lastupdated: "2018-11-02"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# VLAN Spanning
{: #vlan-spanning}

VLAN spanning enables all devices on an account to communicate with each other by means of the private network, regardless of the devices assigned VLAN.
{: #shortdesc}

## Understanding VLAN spanning
{: #understanding}


In {{site.data.keyword.Bluemix}}, VLAN spanning can be used for many different purposes and has an impact on device communication. To learn more about the basics of VLAN spanning before you get started, review the following information.
{: shortdesc}

### How VLAN spanning works

By enabling VLAN spanning, all of your routed traffic is able to travel between all private subnets, across all private VLANs on your account. This serves business needs that require the global communication of your routed traffic. For example: Enable VLAN spanning if devices residing on more than one private subnet need to communicate, whether on the same or different VLANs.

**Note**: When spanning is enabled, it affects the entire account. You cannot exempt any subnets, VLANs or devices from VLAN Spanning. If you currently rely solely on private subnets to segregate servers into roles or tiers, enabling VLAN spanning removes that segregation.

### Default values

By default, VLAN spanning is disabled. Devices located on two different private subnets, whether on the same or different VLANs, will not be able to send IP traffic to one another.

### Services that commonly require VLAN spanning

Specific tutorials are available to help you set up VLAN spanning for your situation. See our links to [Other resources](other-resources.html).


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

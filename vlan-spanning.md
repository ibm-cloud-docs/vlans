---

copyright:
  years: 1994, 2017, 2018, 2019
lastupdated: "2019-02-28"

keywords: VLAN Spanning VLAN, Default values, VLAN Spanning

subcollection: vlans

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:DomainName: data-hd-keyref="DomainName"}
{:note: .note}
{:important: .important}
{:deprecated: .deprecated}
{:generic: data-hd-programlang="generic"}


# VLAN Spanning
{: #vlan-spanning}

VLAN spanning enables all devices on an account to communicate with each other by means of the private network, regardless of the devices assigned VLAN.
{: #shortdesc}

## Understanding VLAN spanning
{: #understanding-vlan-spanning}


In {{site.data.keyword.Bluemix}}, VLAN spanning can be used for many different purposes and has an impact on device communication. To learn more about the basics of VLAN spanning before you get started, review the following information.
{: shortdesc}

### How VLAN spanning works
{: #how-vlan-spanning-works}

By enabling VLAN spanning, all of your routed traffic is able to travel between all private subnets, across all private VLANs on your account. This serves business needs that require the global communication of your routed traffic. For example: Enable VLAN spanning if devices residing on more than one private subnet need to communicate, whether on the same or different VLANs.

When spanning is enabled, it affects the entire account. You cannot exempt any subnets, VLANs or devices from VLAN Spanning. If you currently rely solely on private subnets to segregate servers into roles or tiers, enabling VLAN spanning removes that segregation.
{:note}

### Default values
{: #vlan-spanning-default-values}

By default, VLAN spanning is disabled. Devices located on two different private subnets, whether on the same or different VLANs, will not be able to send IP traffic to one another.

### Services that commonly require VLAN spanning
{: #vlan-spanning-services}

Specific tutorials are available to help you set up VLAN spanning for your situation. See our links to [Other resources](/docs/infrastructure/vlans?topic=vlans-other-resources-vlan-spanning).


## Managing VLAN spanning
{: #manage-vlan-spanning}

You can enable or disable VLAN spanning for your account.
{: shortdesc}

To update your account setting, follow these steps:

  1. From your browser, open the [{{site.data.keyword.Bluemix_notm}} console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://{DomainName}/){: new_window} and log into your account.
  2. In the menu, select **Classic Infrastructure**. The Customer Portal opens.
  3. In the Customer Portal navigation, select **Network > IP Management > VLANs**.
  4. Select the **Span** tab to access the VLAN Spanning section.
  5. Select the **On** or **Off** radio button as desired to enable or disable VLAN spanning respectively.

Toggling VLAN Spanning within a short amount of time might result in delayed application.
{:note}

The update request can take up to 15 minutes to process. A confirmation of the change displays on the screen. You can update your VLAN spanning settings at any time by repeating the previous steps.

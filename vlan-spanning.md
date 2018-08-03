---
copyright:
  years: 1994, 2017
lastupdated: "2018-08-03"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# VLAN Spanning

VLAN Spanning enables routed traffic to travel between all of your account's
VLANs and subnets on the private network, globally. By default, devices located
on two different private VLANs, and even subnets within the same VLAN, may not
send IP traffic to one another. By enabling VLAN Spanning, these restrictions
are lifted. This means that all devices on the private network will be able to
communicate. Note that it is not possible for you to specify sets of VLANs or
devices for which VLAN Spanning is not applied.


## When should I enable VLAN Spanning?

VLAN spanning should be enabled whenever the business need arises. For example,
if devices that reside on more than one private subnet, or between multiple
VLANs, need to communicate, VLAN spanning should be enabled.


## Managing VLAN Spanning

Follow these steps to enable or disable VLAN Spanning for your account:

  1. From your browser, open the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.bluemix.net/){: new_window} and log into your account.
  2. In the menu, select **Infrastructure**. The Customer Portal opens.
  3. In the Customer Portal navigation, select **Network > IP Management > VLANs**.
  4. Select the **Span** tab to access the VLAN Spanning section.
  5. Select the **On** or **Off** radio button as desired to enable or disable VLAN Spanning respectively.

### What Happens Next

After updating VLAN spanning selections, the request may take up to 15 minutes
to process. A confirmation of the change will  appear below the Span tab. VLAN
spanning settings may be updated at any time by repeating these steps.

  **Note: Toggling VLAN Spanning within a short amount of time may result in delayed application.**

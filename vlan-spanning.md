---
copyright:
  years: 1994, 2017
lastupdated: "2017-12-27"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Enable or Disable VLAN Spanning

Sometimes, multiple private network VLANs can exist on a single customer account. However, network devices are unable to communicate with each other on the private network if they do not exist on the same VLAN. VLAN spanning enables all devices on an account to communicate with each other by means of the private network, regardless of its assigned VLAN. 

VLAN spanning service applies to all devices on the account; spanning may not be applied to specific VLANs or to specific devices. VLAN spanning may be enabled or disabled as necessary, and it takes approximately 15 minutes to process, once a change to the setting has been made. Follow the steps given in this article to enable or disable VLAN spanning on an account.


1. From your browser, open the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/){: new_window} and log into your account.
2. In the Customer Portal navigation, select **Network > IP Management > VLANs**.
3. Select the **Span** tab to access the VLAN Spanning section.
4. Select the **On** radio button to enable VLAN spanning. Choose the **Off** radio button to disable VLAN spanning.

## What Happens Next

After updating VLAN spanning selections, the request may take up to 15 minutes to process. A confirmation of the change will  appear below the Span tab. If you enable VLAN spanning, devices can communicate with one another across VLANs using the private network. If you disable spanning, devices can connect to one another only if they reside in the same VLAN; cross-VLAN communication no longer is enabled. VLAN spanning settings may be updated at any time by repeating the steps given in this article. **Note:** Toggling between VLAN spanning settings in a short amount of time may result in a delay of settings being applied.

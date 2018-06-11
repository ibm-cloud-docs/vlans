---
copyright:
  years: 1994, 2017
lastupdated: "2018-06-06"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Allow servers to communicate by the private network across multiple VLANs

**For cross-connects between two or more servers.**

 * Our private network is your cross-connect. Your first server purchase generates a private VLAN for your account with 64 private IPs.
 * All of your future server purchases are placed on the same VLAN so that your servers can communicate over the private network.
 * If you expect to have more than 64 servers, the VLAN automatically grows as needed. There is no need to open a support ticket.
 * We cannot always guarantee that your servers will be placed behind the same routers, or if you have servers in multiple locations you will need to Enable Private Network Spanning via the portal.

You can do this setup task by following these steps:
1. Open the [IBM Cloud console ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.bluemix.net/){: new_window} and log into your account.
2. In the menu, select **Infrastructure**. 
3. In the Customer Portal navigation, select **Network > IP Management > VLANs + Span (tab)**.
4. You will be brought to the screen where you can select **Yes** and then select **Update VLAN span setting** to complete the setup process.

---
copyright:
  years: 1994, 2017
lastupdated: "2017-11-29"
---
{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Allow servers to communicate by the private network across multiple VLANs

**For cross-connects between two or more servers.**

 * Our private network is your cross-connect. Your first server purchase generates a private VLAN for your account with 64 private IPs.
 * All of your future server purchases are placed on the same VLAN so that your servers can communicate over the private network.
 * If you expect to have more than 64 servers, the VLAN automatically grows as needed. There is no need to open a support ticket.
 * We cannot always guarantee that your servers will be placed behind the same routers, or if you have servers in multiple locations you will need to Enable Private Network Spanning via the portal.

You can do this setup task in the [Customer Portal ![External link icon](../../icons/launch-glyph.svg "External link icon")](https://control.softlayer.com/) by selecting **Network -> IP Management -> VLANs + Span (tab)**.

You will be brought to the screen where you can select **Yes** and then select **Update VLAN span setting** to complete the setup process.

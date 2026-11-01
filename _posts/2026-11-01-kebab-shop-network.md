---
title: Wiring a kebab shop from bare stone
excerpt: "When I got to the new location, there was absolutely nothing. The owner had stripped the place down to the bare stone."
date: 2026-11-01 15:47:00 +0000
series: Kebab shop
series_parts: 7   # planned; the box shows 'Part X of 7' until they're all out
tags: [local-shops, networking]
image: https://res.cloudinary.com/haazen/image/upload/Kebab%20shop/network-cubby.jpg
header_image: false   # list + link previews; the photo is already in the story
---

> **Note:** the network went in about four years ago, long before I used Claude, so that was all me. When the EC200a died recently, Claude helped me pick the replacement NVR and its disk size. And it helped me write this up.

When I got to the new location, there was absolutely nothing. The owner had stripped the place down to the bare stone.

And he wanted everything: Wi-Fi, cameras, the register, TVs. At the start he even wanted an office spot in the basement. (That never happened.)

## A 500 m spool of Cat6

Walls stripped to the stone is the best possible moment to run cable. So I gave him my 500 m spool of fire-rated Cat6. I'd picked it up at an outlet sale for €135 ages ago, and it had been waiting for a use ever since. Finally.

The deal: he pulls cable wherever he thinks he'll need it, because I didn't feel like pulling it myself. I helped plan the main runs: down to the basement, to the camera spots, to where the TVs would hang, and into the kitchen.

Most runs end up above the fuse box, in their own separate area, at the main switch. The kitchen and the cameras at the back run to the kitchen switch instead.

![The network corner above the fuse box: main switch, Ziggo router, and a lot of turquoise Cat6](https://res.cloudinary.com/haazen/image/upload/Kebab%20shop/network-cubby.webp)
 And I still have about half a freaking spool left.

## The network

I kept it simple: one network, straight off the Ziggo router, with TP-Link Omada switches and access points.

Customers get Wi-Fi too, on their own SSID but the same flat network. The card machines don't touch it at all: they all run on 4G. And unlike [the sandwich shop's guest Wi-Fi](/2026/11/linksys-on-a-zip-tie/), I set it up properly this time: the customer SSID is marked as a guest network in Omada, so customers can't see each other's devices or reach anything on the shop's network, like the registers or the cameras.

The one exception to the flat network: the TVs. They run on an HDMI-over-IP setup that blasts uncontrolled multicast everywhere, and it did not play nice with the rest of the network. So it got its own VLAN. It even refused to work until I disabled IGMP snooping on that VLAN, which means its multicast just floods every port in it. Fine, as long as it stays in its own little box. More on that in part 5.

## The gear

| Where | Device |
|---|---|
| Main switch | TP-Link Omada SG2016P |
| Kitchen switch | TP-Link Omada SG2016P |
| Counter switch | TP-Link Omada SG2008P |
| Center access point | TP-Link Omada EAP653 |
| Kitchen access point | TP-Link Omada EAP225 |

It didn't start out like that. Version one was just the two 16-port switches and a single access point in the center. Then it turned out the kitchen sits behind a thick concrete wall that Wi-Fi just doesn't get through, so the kitchen got its own.

The Omada controller first ran as software on an HPE EC200a, a little server I lent him. Semi-permanently. It ran Proxmox, with Agent DVR for the cameras and Home Assistant for the smart lighting next to the controller. Those two get their own parts later in this series.

That's actually why there's a counter switch at all. The EC200a needed ports for its iLO, for Proxmox, and for everything running on it, so it got a €10 TP-Link switch from Action. That did its job, right up until the registers needed PoE. Now it's an Omada SG2008P like the rest, and it outlived the server it was bought for: these days it runs a TV, the NVR, and the new POS systems that went in last year (part 3).

The EC200a itself lasted until recently, when its hard drive died. The cameras moved to a proper NVR (more on that in part 7), and the Omada controller moved to TP-Link's cloud. One less box to babysit.

![The Dahua NVR, on the shelf where the EC200a used to live, on top of the audio gear (that's part 4)](https://res.cloudinary.com/haazen/image/upload/Kebab%20shop/nvr-shelf.webp)

## The worst part

Replacing that €10 switch. Its uplink is a cable coming out of the wall that's only just long enough to reach. So guess what I also didn't have to mount? The new switch is held in place by its cable.

![The counter switch, standing upright, held in place by nothing but its cables](https://res.cloudinary.com/haazen/image/upload/Kebab%20shop/counter-switch.webp)

Again. See also: [the RCM sensor in my EV charger](/2026/11/ev-charger-build/) and [the router on a zip tie](/2026/11/linksys-on-a-zip-tie/). At this point it's less a coincidence and more a mounting strategy.

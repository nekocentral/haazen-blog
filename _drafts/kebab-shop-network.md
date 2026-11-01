---
title: Wiring a kebab shop from bare stone
series: Kebab shop
tags: [local-shops, networking]
---

When I got to the new location, there was absolutely nothing. The owner had stripped the place down to the bare stone.

And he wanted everything: Wi-Fi, cameras, the register, TVs. At the start he even wanted an office spot in the basement. (That never happened.)

## A 500 m spool of Cat6

Walls stripped to the stone is the best possible moment to run cable. So I gave him my 500 m spool of fire-rated Cat6. I'd picked it up at an outlet sale for €135 ages ago, and it had been waiting for a use ever since. Finally.

The deal: he pulls cable wherever he thinks he'll need it, because I didn't feel like pulling it myself. I helped plan the main runs: down to the basement, to the camera spots, to where the TVs would hang, and into the kitchen.

Every network run ends up above the fuse box, in its own separate area. And I still have about half a freaking spool left.

## The network

This time I kept it simple: one network, straight off the Ziggo router, with TP-Link Omada access points for the Wi-Fi. And this time with client isolation turned on, unlike [the sandwich shop's guest Wi-Fi](/2026/11/linksys-on-a-zip-tie/).

The gear:

| Where | Device |
|---|---|
| Main switch | TP-Link Omada SG2016P |
| Kitchen switch | TP-Link Omada SG2016P |
| Counter switch | TP-Link Omada SG2008P |
| Center access point | TP-Link Omada EAP653 |
| Kitchen access point | TP-Link Omada EAP225 |

It didn't start out like that. The first version was the two 16-port switches and a single access point. At first there was one access point, an EAP620 HD, until it turned out the kitchen sits behind a thick concrete wall that Wi-Fi just doesn't get through. So the kitchen got its own.

And the counter switch was originally a €10 TP-Link switch from Action. It did its job, right up until the registers needed PoE. Now it's an Omada one like the rest.

Originally, the Omada controller ran as software on an HPE EC200a, a little server I lent him. Semi-permanently. It also ran Agent DVR for the cameras and Home Assistant for the smart lighting, but those get their own parts later in this series.

That lasted until recently, when its hard drive died. The cameras moved to a proper NVR (more on that in part 7), and the Omada controller moved to TP-Link's cloud. One less box to babysit.

Customers get Wi-Fi too, on that same flat network. The card machines don't touch it at all: they all run on 4G. And this time I actually set up client isolation, so customers can't see each other's devices.

## TODO: the worst part

---
title: I told him not to buy Lidl cameras
tags: [cctv, networking, sandwich-shop]
image: TODO-cloudinary-url
---

Same sandwich shop as [the router on a zip tie](/2026/11/linksys-on-a-zip-tie/). TODO: fix this link's date once that post is published.

When the owner wanted cameras, I told him: don't be a cheap ass and get cameras from Lidl. Did he listen? No.

## Round one: Lidl

They kept dropping off the Wi-Fi. And when they were connected, the app often just wouldn't connect to them. Cameras that only sometimes record aren't much of a camera system.

## Round two: Dahua

This time he did listen. The shop now has four Dahua cameras, with a fifth one planned, all wired with PoE straight from a Dahua NVR. No more Wi-Fi to drop off.

The NVR lives in the ceiling, out of sight and out of reach, with 4 TB of storage. Heat hasn't been an issue up there.

TODO: any cable-pulling stories?

## The network

The NVR plugs into the KPN modem, and the cameras hang off the NVR's own PoE ports, on their own network. The card machine and register have their own router from the company that manages them, and guests are on the Linksys, blocked from the rest. There's a diagram in [the router post](/2026/11/linksys-on-a-zip-tie/).

TODO: how remote viewing works (Dahua app/P2P, port forward, or none).

## Keeping footage (not too long)

In the Netherlands, the Autoriteit Persoonsgegevens says camera footage should normally be kept for no more than four weeks, unless something happened. The NVR is set to delete anything older than 28 days. If there's ever an incident, that clip gets exported and kept separately.

TODO: confirm the 28-day setting is changed before publishing.

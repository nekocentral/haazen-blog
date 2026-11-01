---
title: I told him not to buy Lidl cameras
series: Sandwich shop
tags: [local-shops, cctv, networking]
image: TODO-cloudinary-url
---

The shop had a couple of break-ins. First their cash register got stolen, so I lent them one of mine. Then the fuckers stole that one too.

So when the owner wanted cameras, I told him: don't be a cheap ass and get cameras from Lidl. Did he listen? No.

## Round one: Lidl

They kept dropping off the Wi-Fi. And when they were connected, the app often just wouldn't connect to them. Cameras that only sometimes record aren't much of a camera system. One of them is actually still hanging by the window. Still powered, too. A monument to cheap-assery.

## Round two: Dahua

This time he did listen. The shop now has four Dahua cameras, with a fifth one planned for the staff side, covering the windows. Those are covered in full-height stickers, so it can't see outside, and the staff all know about the cameras. All of them are wired with PoE straight from a Dahua NVR. No more Wi-Fi to drop off.

The NVR lives in the ceiling, out of sight and out of reach, with 4 TB of storage. Heat hasn't been an issue up there.

Getting the cables there was the worst part. Four Cat5e cables through a single normal conduit meant for one or two. It took my mate and me an hour or two of pulling, pushing and swearing. Apparently every project of mine involves forcing too many cables through too small a hole (see also: [the EV charger](/2026/11/ev-charger-build/)).

## The network

The NVR plugs into the KPN modem, and the cameras hang off the NVR's own PoE ports, on their own network. The card machine and register have their own router from the company that manages them, and guests are on the Linksys, blocked from the rest. There's a diagram in part 1.

Remote viewing goes through Dahua's DMSS app. It connects through Dahua's own cloud service, so there's no port forward on the KPN modem and the NVR isn't exposed to the internet directly. The trade-off is relying on Dahua's cloud, and keeping the NVR's firmware up to date.

## Keeping footage (not too long)

In the Netherlands, the Autoriteit Persoonsgegevens says camera footage should normally be kept for no more than four weeks, unless something happened. The NVR is set to delete anything older than 28 days, and there's a camera sticker at the entrance so everyone knows they're being filmed. If there's ever an incident, that clip gets exported and kept separately.

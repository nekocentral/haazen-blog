---
title: My router has been hanging from a zip tie for six years
tags: [networking, tomato, wifi]
image: TODO-cloudinary-url-of-the-2021-photo
---

The sandwich shop at my local train station has my old Linksys router hanging from a zip tie. I put it there around 2020, and it's still there.

They wanted guest Wi-Fi they could switch off in the evening. So I flashed my old Linksys with Tomato, set a schedule, and zip-tied it to the wall.

About half a year later their KPN modem died, taking the debit card machine and the phone with it. I dropped off a Stonesoft FW-315 firewall and an ATA from my own spare kit to bridge the gap. A week or two later KPN sent a new modem and my gear went home. The Linksys stayed.

![The setup in 2021: the Linksys hanging top right, my temporary Stonesoft firewall on the shelf](TODO-cloudinary-url-of-the-2021-photo)

## The setup

The router is a Linksys TODO-model from the Cisco era. I started out on Shibby's Tomato build, and I think it's on FreshTomato now. Tomato has a built-in schedule for the wireless, so the guest Wi-Fi is on during opening hours and switches itself off after closing, without anyone having to remember. Not that many people use it, I think, but it's there.

TODO: rate limit. If there is one, what's it set to?

## The captive portal that never was

The plan was a simple "click to accept" page, stored on a USB stick plugged into the router. Captive portals were a pain in the arse to get working back then: you have to block access but still allow just enough for the portal page itself to load. I fought with it for a while and then just gave up.

## Keeping guests away from the till

These days the shop's network looks like this:

```
                    KPN modem
       ┌───────────────┼───────────────┐
    Linksys      Payment company      Dahua NVR
  (guest Wi-Fi)    router (card       (camera
                 machine + till)      network)
```

The KPN modem sits in the middle, and everything else hangs off it on its own network: the Linksys for guests, a router from the company that manages the card machine and register, and the NVR for [the cameras](/TODO-cameras-post-link/).

NAT on its own only blocks one direction, though: guests could still reach out to anything on the KPN side. So, if I remember right, I also added a firewall rule on the Linksys that blocks the KPN LAN range for guests, and I tested it: from the guest Wi-Fi I couldn't reach anything on the LAN. Client isolation is on too, so guests can't see each other either.

## Six years later

It's had no firmware updates since it went up. TODO: what you find when you log in again (if the password still works).

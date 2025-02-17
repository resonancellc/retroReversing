---
layout: post
tags:
- devkit
- hardware
- saturn
- sega
title: Official Sega Saturn Development Kit (Hardware)
published: true
thumbnail: /public/consoles/Sega Saturn.png
youtube: 3E4Gvue9Im8
image: /public/SaturnProgrammingBox.jpg
permalink: /sega-saturn-programming-box/
breadcrumbs:
  - name: Home
    url: /
  - name: Development Kits
    url: /devkit
  - name: Official Sega Saturn Development Kit (Hardware)
    url: #
recommend: devkit
editlink: /sega/saturn/SegaSaturnProgrammingBox.md
references:
  - segaretro.org
  - youtube
---

During the sega saturns lifecycle there were multiple development kits available to developers starting from the original Sphia Systems that came out before the retail hardware, followed by devkits from both `Cross Products` (Official) and the Unofficial `SN Systems (PSYQ)`.

# Sega Saturn Programming Box (Sophia Systems)
<img src="/public/SaturnProgrammingBox.jpg" />
The original Sega Saturn Programming box (or P-Box) became available to developers before the retail release of the Saturn and was the first development kit available for the Saturn [^1].

The Sophia needs to have 2 processors installed to be a working development system but occasionally people sell the systems with only one processor. If only one processor is present it will still boot to dashboard but you won't be able to run anything.

These were later replaced by the CartDev development kit but the new CartDev also had configuration options to connect to the older P-Box.

The P-Box had a DIP switch to change between the built in CD emulator (which booted from hard drive) to the actual CD drive, so developers could load their game on the built in hard drive instead of burning a CD each time they wanted to test.

The P-Box also has a custom Japanese-only SCSI connection to the developers PC (or SGI Indy) so the developer could send game builds to the system and debug games from the PC interface.

---
# Sega of America's Cart Dev
￼<img src="/public/images/saturn/P-BOX_and_CartDev.png" />
￼
The CartDev system was a much cheaper alternative to the Sophia P-Box costing just $4,800 instead of the $7,475 for the P-Box.
￼<img src="/public/images/saturn/Sega_CartDev_1.jpg" />

There are 2 versions of the CartDev kit:
* Cross CartDev Rev.A
* Cross CartDev Rev.B

The following youtube video shows a CartDev in action:
<iframe width="560" height="315" src="https://www.youtube.com/embed/qKH07vPTC7w" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


## Connecting CartDev To the old P-Box
￼<img src="/public/images/saturn/ConnectCartDevToPBox.png" />


## Connecting CartDev to modified retail Saturn
￼<img src="/public/images/saturn/ConnectCartDevToRetailSaturn.png" />

---
# Cross Products Dev Kit
￼<img src="/public/images/saturn/CrossProductsCartDev.png" />

According to the article in EDGE Cross Products has just been bought by SEGA and were in charge of supplying the CartDev, Mirage CD Emulator and Modified Saturn to game development studios [^3].

The Software Development Kit that was provided with these systems were also provided by Cross Products and were under the `SNASM2` SDK brand name. This provided all the standard libraries, compilers and other build tools to create Saturn games.

# Modified Sega Saturn
The Modified Sega Saturn that Cross Products sold to game developers was known as the `DevSaturn` and can be seen in this sort youtube video:
<iframe width="560" height="315" src="https://www.youtube.com/embed/72Ac7R5TMuk" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

It cost $700 and it was not able to run burned CDR games without the `System Boot Disc` so there was no benefit to non-developers for owning the modified unit.

It has a DIP switch on the side to switch between the CD emulator and the actual CD drive inside the saturn. 
It also has a connection port on the left hand side of the unit along side a Cross Products Logo. This is where it would connect to the Mirage CD emulator from Cross Products.

You can see the back of the modified saturn with the cross products CD Switch in a photo taken by `stevejigga` and posted on the AssemblerGames forum:
￼<img src="/public/images/saturn/CrossProducts_Saturn_CD_Switch.jpg" />

The official price list from Cross Products put the Modified Saturn by itself at a price of £500 with a brief description:
> Production Saturn fitted with shielded NMI cables and CD switch 

Presumably the modification to be able to use the CD emulator is the only modification made to the retail saturn units, but its also possible they enabled running CD-Rs without using the Sega Saturn Boot disc, but this is unconfirmed.

# Address Checker Hardware by SI Electronics
￼<img src="/public/images/saturn/SegaSaturn_Address_Checker.jpg" />

In order to make sure your game doesn't violate the Sega Memory usage guide this piece of hardware would allow running your game with real-time checking of the memory addresses used. 

If the game accessed memory in certain restricted regions this machine would send an error message to an attached PC. Apart from that functionality it is exactly the same as a retail Saturn console (including the need for System Disc to run CD-Rs).

This machine would likely be used by Sega themselves to check if games can be given the go-ahead to be produced, otherwise they would be failed and given back to the developer to fix the memory issues.

NFGGames has a good page on the original `SI Electronics` Address checker here: [IS Electronics / Sega Saturn Address Checker - NFG Games](https://nfggames.com/games/satadd/)

For the second version of the Sega Saturn Address checker hardware it was basically a retail Saturn with LED lights down the side, one for each unmapped memory area, for more information SEGARetro has an excellent wiki page on it: [Sega Saturn Address Checker - Sega Retro](https://segaretro.org/Sega_Saturn_Address_Checker)

---
# Sega Saturn Boot DIsc
Similar to the Dreamcast's System Disc 2, this is a disc that allows any retail Sega Saturn to play developer written CD-Rs without any Saturn modding required.

<iframe width="560" height="315" src="https://www.youtube.com/embed/jdOdhjv1FNY" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

This is very useful for developers as they could burn CD-Rs and pass them off to the testing team that just need the system disc and the burned CD-R [^4].

There are two versions available, one in red and the other in black, one can only be used for Sega first party titles as it was only used in-house at Sega. The other was given to 3rd party developers and only boots 4rd party games.

Note that when using the system disc it will go back to the dashboard and disable the security check, so just pop the CD-R disc into the drive and it should boot as normal.

---
# Mirage CD Emulator
<iframe width="560" height="315" src="https://www.youtube.com/embed/BQwD0asDiic" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
The Mirage CD Emulator was developed by Cross Products and sold to development studios to save time and discs by emulating the use of a physical drive.

It cost $3000.00 to buy directly from SEGA and contained a 1gb hard drive inside, allowing for a couple of games to be stored on it.

Similar to mounting an ISO on a PC, although instead of ISO the Mirage used a custom format that needed to be created with special development kit tools.

This allowed developers to simulate errors with the disc to make sure their game was as robust as possible.

For more information about the Mirage please check out this excellent page on SegaRetro: [MIRAGE Universal CD Emulator](https://segaretro.org/MIRAGE_Universal_CD_Emulator)

The Mirage wasn't the only way to mount discs for the development system, there was also a Virtual CD emulator available for the P-box. This allowed much more discs to be mounted as it could use the entire PC hard drive as storage.

---
# Hitachi E7000 PC Debug Unit (ICE)
￼<img src="/public/images/saturn/Hitachi-E7000-PC-Debug-Saturn.jpg" />
The Hitachi E7000 PC Debug Unit is an In Circuit Emulator or ICE for short, it connects to the Sophia (P-Box) or the Address Checker hardware and also the developers PC.

This was used by developers to debug their games and it acted as a full SH-2 cpu. It was not cheap as one unit cost $15,000.00 USD including all wires and documentation, so not all developers could have one of these units.

You can use the `ipi` executable included with the hitachi development kit to connect to it as shown in the video below:
<iframe width="560" height="315" src="https://www.youtube.com/embed/yUgepCl0J0w" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

---
# Hardware for Designers
Sega recommended Macintosh for sound designers or 2D Artists, and SGI INDY or INDIGO2 machines for 3D work. Sega also released a couple of hardware attachments for Macintosh systems specifically for these designers.

## Sound Target Box by Sophia Systems
￼<img src="/public/images/saturn/Sophia-Sega-Saturn-Sound-Box-byPeekB.jpg" />
For sound designers a `Sound Box` could be purchased for $4,800.00 from SEGA and connected to the sound designers Macintosh system.

## Graphics Target Box by Sophia Systems
￼<img src="/public/images/saturn/Saturn-Graphics-Box-ChrisMCovell.jpg" />
For Graphics Designers a `Graphics Box` can be purchased from Sega. This image was from `Chris M Covell`[^6] and you can checkout his excellent site here: [Sega Saturn Graphics Box](https://www.chrismcovell.com/saturnbox.html).

---
# Others
* Blue Cart (PsyQ)
* Cross Products VCD/CD board


# References
[^1]: https://segaretro.org/Sega_Saturn_Programming_Box
[^2]: https://segaretro.org/Sophia_Systems
[^3]: EDGE Magazine issue 23 (August 1995)
[^4]: [(198) Sega Saturn System Boot Disc (Play Backups Without Modding!) - Game Taff - YouTube](https://www.youtube.com/watch?v=jdOdhjv1FNY)
[^5]: [Ebay: Hitachi E7000 PC Saturn SH-2 Debugging station | ASSEMbler - Home of the obscure](https://assemblergames.com/threads/ebay-hitachi-e7000-pc-saturn-sh-2-debugging-station.3092/)
[^6]: [Sega Saturn Graphics Box](https://www.chrismcovell.com/saturnbox.html)

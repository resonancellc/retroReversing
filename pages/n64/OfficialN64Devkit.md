---
layout: post
tags: 
- n64
- devkit
- hardware
title: Official Nintendo 64 (Ultra 64) Development Kit Hardware
thumbnail: /public/consoles/Nintendo 64.png
videocarousel:
  - title: Partner N64
    image: http://img.youtube.com/vi/d5YO2XMBvvk/hqdefault.jpg
    youtube: d5YO2XMBvvk
  - title: 
    image: http://img.youtube.com/vi/Z45nbzMLk98/hqdefault.jpg
    youtube: Z45nbzMLk98
image: /public/magazine/EDGE_20_SGI_Onyx.png
permalink: /official-n64-devkit/
breadcrumbs:
  - name: Home
    url: /
  - name: Nintendo 64
    url: /n64
  - name: Official Nintendo 64 (Ultra 64) Development Kit Hardware
    url: #
recommend: n64
editlink: /n64/OfficialN64Devkit.md
references:
  - archive.org
---

The website N64Squid has a page dedicated to Nintendo 64 development hardware that is well worth a look: [Nintendo 64 development hardware - N64 Squid](https://n64squid.com/homebrew/n64-sdk/development-hardware/). This page aims to compliment that page and give additional details about the hardware, so it is recommended you read that page first [^3]. 

# Official Development Kit 

## Early Development Hardware - SGI Onyx 
<section class="postSection">
<img src="/public/magazine/EDGE_20_SGI_Onyx.png" class="wow slideInLeft postImage" />

<div markdown="1">

In the very early days of the Ultra 64 project the retail hardware was still under active development, but games would need to start development as soon as possible so that the system could have launch titles.

As there was no ready hardware to use early developers for the platform used the `SGI Onyx` as it was presumed that the hardware would be very similar, they were envisioning the N64 as just a stripped down version of this workstation, mainly due to their partnership with SGI for the graphics.


The earliest mention of the SGI Onyx being used as an early development kit for the Nintendo 64  was in the Edge UK magazine issue 20 from May 1995. [^1].

</div>
</section>


## Nintendo 64 Development Unit (IRIX workstations)
<section class="postSection">
<img src="/public/N64/sgiDevkit.jpg" class="wow slideInLeft postImage" />

<div markdown="1">

As the N64 hardware matured so did the development hardware, the `Nintendo 64 Development Unit` was one of there first evolutions of the development kit and was sold directly by Nintendo from October 1996 onwards.

It consisted of a standard SGI Indy workstation with an add-on board containing the N64 hardware. 

This has the benefit of not using any workstation hardware resources to run the games as it used the N64 hardware directly and just communicated with it for debugging [^9].

</div>
</section>


### N64 hardware add-on board (Nintendo 64 Development Board)
<section class="postSection">
    <img src="/public/N64/n64AddOnInternals.jpg" class="wow slideInLeft postImage" />
<div markdown="1">
The add-on board slips into the SGI Indy workstations case and has pretty much all the hardware from a retail console, with a few changes to allow the communication between the IRIX operating system and the hardware.

</div>
</section>


### N64 Hardware Connectivity
<section class="postSection">
    <img src="/public/N64/SGI_Indy_card_back.jpg" class="wow slideInLeft postImage" />
<div markdown="1">
You can see the standard SNES/N64 A/V out socket in the back on the Indy, apart from this the connectivity was very sparse. The controllers connected via another bit of hardware and are not on the add-on board at all.

If you look closer you will notice that there is a number of ethernet ports which actually go to the add-on board. These are used to connect to multiple development hardware including an adapter for retail controllers which can be seen in a tweet from Shane Battye .
</div>
</section>

 <blockquote class="twitter-tweet" data-conversation="none"><p lang="en" dir="ltr">But wait a minute; don’t u64 development boards require a ‘Joybus’ adapter? <br>Yep, but only if they’re interfacing with retail type controllers (which may have been available not too long after RJ-11 development controllers)... <a href="https://t.co/kY3wOjPQug">pic.twitter.com/kY3wOjPQug</a></p>&mdash; Shane Battye (@shanebattye) <a href="https://twitter.com/shanebattye/status/1175540587941879808?ref_src=twsrc%5Etfw">September 21, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 


---
## KMC Partner-N64
The `Nintendo 64 Development Unit` later evolved into the `Partner-N64` series of hardware by KMC (Kyoto Microcomputer, Co. Ltd.) and consisted not only of hardware for the SGI workstations but also created a version that worked on standard Windows PCs!

### KMC Partner-N64NW (Network SGI workstations)
Unlike the `Nintendo 64 Development Unit` this development kit didn't contain an add-on board and instead connected directly to a modified retail N64. This was achieved using a custom cartridge known as a `Debugger Pak` slotted in the N64 with a network adapter that could be connected directly to an SGI workstation such as an Indy [^14].

### KMC Partner-N64PC (Windows PCs)
The Partner-N64PC was another full official development kit by KMC (Kyoto Microcomputer, Co. Ltd.) specifically for Windows PCs. 

The SDK that comes with the Partner-N64PC was provided by Metrowerks (Codewarrior).

### Partner-N64 Debugger Pak 

<section class="postSection">
    <img src="/public/N64/PARTNER-1J 64.jpg" class="wow slideInLeft postImage" />
<div markdown="1">
The `Debugger Pak` was used by both Partner-N64PC and Partner-N64NW, it functioned similarly to the standard `Game Pak` but were longer and had the connection port at the top for connecting to the PC. This allowed full debugging support such as breakpoints and stack traces to be used.
</div>
</section>




### ISA Card (Dedicated Interface board)

<section class="postSection">
    <img src="/public/N64/PARTNER7IF7I!.jpg" class="wow slideInLeft postImage" />
<div markdown="1">
The ISA card was a small add-on card that could be slotted a the standard PC's ISA bus slot and contained just enough hardware to allow communication over the port. 

The ISA card comes as part of the Partner-N64PC pack but you could also buy a PCI version separately for $350 [^13].

Notice that there are DIP switches at the top of the board that need to be configured before installing to make sure that the I/O addresses for communication match the PC.
</div>
</section>


## Modified N64 (Control Deck Assembly)
<section class="postSection">
    <img src="/public/N64/N64KMCModified.jpg" class="wow slideInLeft postImage" />
<div markdown="1">

In order to use the Partner64 the retail N64 console hardware had to be modified, these normally came with the development kit when you bought the Partner64 or you could buy a separate one for about $200 [^13].

Ultra64.ca has an excellent tutorial which shows you how to *create your own* Partner N64 development kit for home-brew development, very cool! It is available here: [Make your own Partner N64 console, for use with IS Viewer : Nintendo (Ultra) 64](https://ultra64.ca/tutorials/make-your-own-partner-n64-console-for-use-with-is-viewer/)

</div>
</section>

### Usage of Partner64
The official Partner64 development kit was quite popular and used both inside and outside of Nintendo.

Here is a list of games that still contain KMC Partner64 debug code thanks to a Pastebin by user `ZOINKITY` [^8]:
1. KMC\0   1080 TenEighty Snowboarding
2. KMC\0   64 Oozumou 2
3. KMC\0   64 Trump Collection - Alice no Wakuwaku Trump World
4. KMC\0   AI Shougi 3
5. KMC\0   Aidyn Chronicles - The First Mage
6. KMC\0   Battlezone - Rise of the Black Dogs
7. KMC\0   Blues Brothers 2000
8. KMC\0   Brunswick Circuit Pro Bowling
9. KMC\0   Buck Bumble
10. KMC\0   Charlie Blast's Territory
11. KMC\0   Dragon Sword 64 (NTSC) (Proto)  [[NOT PAL!]]
12. KMC\0   Earthworm Jim 3D
13. KMC\0   Elmo's Letter Adventure
14. KMC\0   Elmo's Number Journey
15. KMC\0   Fighter Destiny 2
16. KMC\0   Fighting Force 64
17. KMC\0   GameShark Pro (v2.0)
18. both    Ganbare Goemon - Neo Momoyama Bakufu no Odori / Mystical Ninja Starring Goemon
19. both    Ganbare! Nippon! Olympics 2000
20. KMC\0   Gex 3 - Deep Cover Gecko
21. KMC\0   Gex 64 - Enter the Gecko
22. KMC\0   Glover 2 (USA) (Proto)  [[internal crc B7F40BCF 553556A5]]
23. KMC\0   Harvest Moon 64 / Bokujou Monogatari 2
24. KMC\0   Hercules - The Legendary Journeys
25. both    Hyper Olympics in Nagano 64 / Nagano Winter Olympics '98
26. KMC\0   Ide Yosuke no Mahjong Juku
27. both    International Superstar Soccer 2000
28. both    International Track & Field - Summer Games / International Track & Field 2000
29. both    Jikkyou J.League 1999 - Perfect Striker 2
30. KMC\0   Kakutou Denshou - F-Cup Maniax
31. both    Legend of Zelda, The - Majora's Mask (Debug)
32. KMC\0   Lylat Wars  [[PAL only, not NTSC!]]
33. KMC\0   Mario Party (Europe)    [[not NTSC!]]
34. both    Mario Party 3   [[USA, PAL, +not+ Japan]]
35. KMC\0   Micro Machines 64 Turbo
36. both    Midway's Greatest Arcade Hits - Volume 1
37. KMC\0   Mischief Makers (USA) (Rev A)   [[not in other versions]]
38. KMC\0   MRC - Multi Racing Championship
39. KMC\0   NFL Blitz - Special Edition
40. KMC\0   NFL Blitz 2001
41. KMC\0   Nightmare Creatures
42. KMC\0   Parlor! Pro 64 - Pachinko Jikki Simulation Game
43. KMC\0   Pokemon Puzzle League
44. both    Pokemon Stadium 2 / Pocket Monster Stadium 3
45. KMC\0   Polaris SnoCross
46. KMC\0   Powerpuff Girls, The - Chemical X-Traction
47. KMC\0   Premier Manager 64
48. KMC\0   Ready 2 Rumble Boxing
49. KMC\0   Ready 2 Rumble Boxing - Round 2
50. KMC\0   Road Rash 64
51. KMC\0   Rockman 64 (Japan) (Proto)
52. KMC\0   Star Fox 64 (Rev A) [[Japan and USA; not in v1.0]]
53. KMC\0   Superman (USA) (Proto)  [[not in retail]]
54. KMC\0   Tom and Jerry in Fists of Furry
55. KMC\0   Triple Play 2000
56. KMC\0   WCW Nitro   [[both versions]]
57. both    4567 (64DD)
58. KMC\0   Dezaemon DD (64DD)
59. KMC\0   Doshin the Giant (retail and demo) (64DD)
60. both    Doshin the Giant 2 (64DD)
61. both    Mario Artist Communication Kit (64DD)

---
## Monegi Smart Pack

<blockquote class="twitter-tweet" data-conversation="none"><p lang="en" dir="ltr">Also on display will be a <a href="https://twitter.com/hashtag/64DD?src=hash&amp;ref_src=twsrc%5Etfw">#64DD</a> dev kit with Monegi Smart Pack. These setups were probably the last ‘official’ N64 development systems and likely used for later Hudson titles as well as being sold alongside the CodeWarrior IDE. They supported 512mb ROMs and 64DD out of the box <a href="https://t.co/We3h3ahXa3">pic.twitter.com/We3h3ahXa3</a></p>&mdash; Shane Battye (@shanebattye) <a href="https://twitter.com/shanebattye/status/1180613606892683264?ref_src=twsrc%5Etfw">October 5, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

---
## IS-Viewer 64
<iframe width="560" height="315" src="https://www.youtube.com/embed/AvMoboqlfbA" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

The IS-Viewer64 or IS64 for short was the official way to create a N64 prototype cartridge than ran on a modified version of retail hardware. It is a flash cart created by Intelligent Systems (hence the IS prefix) and was released as part of the official N64 development kit. This did not have debug support such as breakpoints and stack traces and this was much cheaper than alternatives. Although It cost around 1800 USD on release so was still an expensive solution [^6].

The main benefit of the IS-Viewer64 over alternative flash carts available to developers was the crazy fast transfer speed, allowing games to be written to the onboard RAM in as little as 30 seconds! [^7].

### Usage of IS-Viewer64
The IS-Viewer 64 was used to develop the two Zelda games (Oracle of Time, Majoras Mask) and still contains some code to write out debug messages to a connected PC on the retail ROM [^5].

Here is a list of games that still contain IS64 debug code thanks to a Pastebin by user `ZOINKITY` [^8]:
1. Castlevania / Akumajou Dracula Mokushiroku - Real Action Adventure
2. Dance Dance Revolution - Disney Dancing Museum
3. Ganbare Goemon - Neo Momoyama Bakufu no Odori / Mystical Ninja Starring Goemon
4. Ganbare! Nippon! Olympics 2000
5.  Hyper Olympics in Nagano 64 / Nagano Winter Olympics '98
6. J.League Tactics Soccer
7. Mario Artist Paint Studio (64DD)
8. Paper Mario
9. Legend of Zelda, The - Ocarina of Time - Master Quest (Debug)
10. Legend of Zelda, The - Ocarina of Time (Debug)
11. International Superstar Soccer 2000
12. International Track & Field - Summer Games / International Track & Field 2000
13. Jikkyou J.League 1999 - Perfect Striker 2
14. Legend of Zelda, The - Majora's Mask (Debug)
15. Mario Party 3   [[USA, PAL, +not+ Japan]]
16. Midway's Greatest Arcade Hits - Volume 1
17. Pokemon Stadium 2 / Pocket Monster Stadium 3
18. 4567 (64DD)
19. Doshin the Giant 2 (64DD)
20. Mario Artist Communication Kit (64DD)


---
# Unofficial N64 Development Kit

## SN64 (SN Systems)
You can view a cached version of the official Sn systems SN64 development kit thanks to Icequake [SN64 Nintendo64 Development Tools](http://n64.icequake.net/mirror/slaanesh79/Dev/SN%20Systems_files/n64.htm)

<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Check this out!!<br>I recently acquired these <a href="https://twitter.com/hashtag/N64dev?src=hash&amp;ref_src=twsrc%5Etfw">#N64dev</a> cartridges called the “SN64” and the “Maestro64”. <br><br>Manufactured by the company:<br>“SN Systems”. The more Rare of the two is the Maestro64, which was used for N64 Sound development. <a href="https://twitter.com/hashtag/N64?src=hash&amp;ref_src=twsrc%5Etfw">#N64</a> <a href="https://twitter.com/hashtag/RETROGAMING?src=hash&amp;ref_src=twsrc%5Etfw">#RETROGAMING</a> <a href="https://t.co/9vvlB1MOQ7">https://t.co/9vvlB1MOQ7</a> <a href="https://t.co/NRHoj2Uu34">pic.twitter.com/NRHoj2Uu34</a></p>&mdash; Gerry_MAN (@GerryRobotics) <a href="https://twitter.com/GerryRobotics/status/1179955009800286208?ref_src=twsrc%5Etfw">October 4, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

---
# Official Sound Development Tools
Nintendo released multiple hardware for Sound designers to test their creations on the real hardware without having to bug the developers to borrow a full development machine.

The SDK also came with the `N64 Sound Tools` and `MusyX Audio Tools` which contain software such as a sound sample editor which used a format similar to MIDI [^2].

## NUS-SUD (Sound development)

Gerry_MAN has taken some excellent photos of his NUS-SUD on Twitter along with photos of him actually managing to connect and send data from his PC to the hardware!
<blockquote class="twitter-tweet" data-lang="en-gb"><p lang="en" dir="ltr">Check this out!<br>The <a href="https://twitter.com/hashtag/N64dev?src=hash&amp;ref_src=twsrc%5Etfw">#N64dev</a> SoundTools Dev cart streams Music or samples in real-time to the <a href="https://twitter.com/hashtag/N64?src=hash&amp;ref_src=twsrc%5Etfw">#N64</a>. Sent over an LPT printer cable. Notice the white squares? @ the bottom of the screen? <br>Sound PEAK meters!!<br>Inactive when the Cart is not streaming sound.<br>Pretty cool!! <a href="https://twitter.com/hashtag/RETROGAMING?src=hash&amp;ref_src=twsrc%5Etfw">#RETROGAMING</a> <a href="https://t.co/ZpgL1RtSdD">pic.twitter.com/ZpgL1RtSdD</a></p>&mdash; Gerry_MAN (@GerryRobotics) <a href="https://twitter.com/GerryRobotics/status/1182083779915071498?ref_src=twsrc%5Etfw">10 October 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en-gb"><p lang="en" dir="ltr">For the Updated version 3.0 of the ROM you can actually see the pre-existing peak meter pixels as they are just slightly visible...as shown in the image below. Would be cool to get a Version 3 of the SoundTools cart someday. <br>Pretty Awesome!!<br>😎👌 <a href="https://t.co/xAZ8moXAXe">pic.twitter.com/xAZ8moXAXe</a></p>&mdash; Gerry_MAN (@GerryRobotics) <a href="https://twitter.com/GerryRobotics/status/1182085021504589824?ref_src=twsrc%5Etfw">10 October 2019</a></blockquote>
<script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

## Full Devkit used by Sound designers 
The full n64 development kit was used by Sound designer Grant Kirkhope at Rare to produce masterpieces such as Banjo-Kazooie and GoldenEye. This consisted of a Silicon Graphics Indy with the N64 hardware used as an extension inside it [^2].
<blockquote class="twitter-tweet"><p lang="en" dir="ltr">Hmmm I don’t think I did. I had a Silicon Graphics Indy computer with the Ultra 64 circuit board inside it. I connected my PC to it via midi</p>&mdash; Grantilda Von Scarehope (@grantkirkhope) <a href="https://twitter.com/grantkirkhope/status/1182160711377506304?ref_src=twsrc%5Etfw">October 10, 2019</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script>

# References
[^1]: [EDGE 20 1995-05](https://archive.org/stream/EDGE.N020.1995.05/EDGE.N020.1995.05-Escapade#page/n7/mode/2up/search/%22SN+Systems%22)
[^2]: [Gerry_MAN on Twitter](https://twitter.com/GerryRobotics/status/1182083779915071498)
[^3]: [Nintendo 64 development hardware - N64 Squid](https://n64squid.com/homebrew/n64-sdk/development-hardware/)
[^4]: [Make your own Partner N64 console, for use with IS Viewer : Nintendo (Ultra) 64](https://ultra64.ca/tutorials/make-your-own-partner-n64-console-for-use-with-is-viewer/)
[^5]: [IS64 - z64 wiki](http://wiki.spinout182.com/w/IS64)
[^6]: [NESWORLD.COM - IS VIEWER64 (N64 DEVELOPMENT UTILITY)](http://www.nesworld.com/n64-isviewer64.php)
[^7]: [RARE N64 "IS-VIEWER 64" SCSI Development Cartridge - Up and Running!! - Nintendo 64 Forever](https://www.tapatalk.com/groups/nintendo_64_forever/rare-n64-is-viewer-64-scsi-development-cartridge-u-t2605.html)
[^8]: [IS64 and KMC N64 Titles - Pastebin.com](https://pastebin.com/dX0sNss5)
[^9]: [Development Hardware](http://n64.icequake.net/mirror/slaanesh79/Dev/Dev_Hardware.htm)
[^10]: [SN64 Nintendo64 Development Tools](http://n64.icequake.net/mirror/slaanesh79/Dev/SN%20Systems_files/n64.htm)
[^11]: [Nintendo N64 Source code Programming - A Basic Introduction - YouTube](https://www.youtube.com/watch?v=d5YO2XMBvvk)
[^12]: [Partner-N64 PC](http://n64devkit.square7.ch/tools/kmc/part_pc_facts.htm)
[^13]: [Guid to NINTENDO64 development tools](http://n64devkit.square7.ch/tools/tindex.htm)
[^14]: [Development Tools Summary](http://n64devkit.square7.ch/tools/kmc/index.htm)

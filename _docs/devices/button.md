---
title: Button Tentacle
category: Devices
order: 1
---

[<i class="fa fa-arrow-up" aria-hidden="true"></i> Back to Tentacles](/cloud/tentacles)

<iframe width="560" height="315" src="https://www.youtube.com/embed/XzEyqce2l4o?rel=0&amp;controls=0&amp;showinfo=0" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>

## Introduction

Button Tentacle is an open hardware button. It is connected to the Internet via Wi-Fi. It has to be connected to the power via USB cable. Pressing it can trigger action in your [Flow](/cloud/flows).

Button Tentacle is based on the **NodeMCU v2** *(with CP2102 chipset)*. The required open hardware device can be obtained for example from [here](https://goo.gl/QWsBTM).

![NodeMCU v2](/images/nodemcu_v2.png){:width="175px"}

## How to build

> Download and 3D print [a cute 3D Printable Case](https://www.thingiverse.com/thing:2750464) for the Display Tentacle from [Thingiverse](https://www.thingiverse.com/thing:2750464).

### Components

The following components are needed for your *Button Tentacle*:

1. `1x` [NodeMCU v2 CP2102](https://goo.gl/QWsBTM)
2. `1x` USB-A to micro-USB cable

> You will need a 3D Printer if you plan to use the [open source case for Anemone Button Tentacle](#). But you can definitely use the Button Tentacle without any case as well, it just does not look so awesome ;). If you are not sure which 3D printer to buy or use, we can recommend [Prusa i3 MK2S](https://www.prusa3d.com/#our-printer) - we have designed and printed the case on this one.

### Instructions

> No soldering skills or any kinds of nuts is required to assemble this Tentacle

1. Download the 3D printable [open source case for Anemone Button Tentacle](#) from Thingiverse.
2. 3D print it *(detailed instructions how to print it are on the Thingiverse link in step 1.)*
3. Assemble the 3D printed case - it comes in 5 parts.
   1. First you need to put the both small "Y" like legs into the top part of the button - their dimensions are done in a way, that you cannot do it in the wrong way.
   2. Then you should plug the USB cable to your NodeMCU v2.
   3. Then put your NodeMCU v2 into the bottom part. Its legs should fit into the holes in the bottom part nicely.
   4. Then you should put the circular walls/border part on top of the bottom part where your NodeMCU v2 is mounted. Make sure both parts are aligned at the bottom - so your Button Tentacle can stand on the table firmly.
   5. Last step is to gently put the top part with the "Y" like legs attached on the NodeMCU v2. The cone like structure on the bottom side of the top part will press the `Flash` button on the NodeMCU v2 when the button is pressed.
4. Follow the instructions on your Tentacle detail page in the Anemone Dashboard where is described how the generated `.ino` sketch files should be uploaded.

## How to use

Button Tentacle is directly supported by the Anemone IoT Platform. When adding a Tentacle, select a `Button` as its type. *Mr. Cloud* will generate a sketch which can be used to program the *NodeMCU v2* device accordingly. Instructions how to program the device will be shown on your Tentacle detail page together with a button to download the generated sketch `.ino` file.

> The generated `.ino` file uses the well known *Arduino Ecosystem*.

You can use the `Serial Monitor` in the *Arduino IDE* to debug the Tentacle - the Tentacle is writing there what it is doing.

![Button Tentacle](/images/button_tentacle.png)

-----

[<i class="fa fa-arrow-left" aria-hidden="true"></i> Previous chapter: Cloud / Tentacles](/cloud/tentacles) | [Next chapter: Devices / Display <i class="fa fa-arrow-right" aria-hidden="true"></i>](/devices/display)

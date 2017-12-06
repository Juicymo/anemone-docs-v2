---
title: Display Tentacle
category: Devices
order: 2
---

[<i class="fa fa-arrow-up" aria-hidden="true"></i> Back to Tentacles](/cloud/tentacles)

<iframe width="560" height="315" src="https://www.youtube.com/embed/X1juQdLuEpQ?rel=0&amp;controls=0&amp;showinfo=0" frameborder="0" gesture="media" allow="encrypted-media" allowfullscreen></iframe>

## Introduction

Display Tentacle is an open hardware display. It is connected to the Internet via Wi-Fi. It has to be connected to the power via USB cable. It can show some result value from your [Flow](/cloud/flows).

Display Tentacle is based on the **NodeMCU v2** *(with CP2102 chipset)*. The required open hardware device can be obtained for example from [here](https://goo.gl/QWsBTM).

As a display component a low-cost **128x64 OLED i2c Display**. It can be obtained for example from [here](https://goo.gl/KdyzR7).

| ![NodeMCU v2](/images/nodemcu_v2.png) | ![OLED Display](/images/oled_display.png) |

## How to build

### Components

The following components are needed for your *Display Tentacle*:

1. `1x` [NodeMCU v2 CP2102](https://goo.gl/QWsBTM)
2. `1x` [128x64 OLED i2c Display](https://goo.gl/KdyzR7)
3. `1x` [Breadboard SYB-170](https://goo.gl/SUrXJG)
4. `4x` Male to Female 10cm Jumper Cable
5. `1x` USB-A to micro-USB cable

> You will need a 3D Printer if you plan to use the [open source case for Anemone Display Tentacle](#). But you can definitelly use the Display Tentacle without any case as well, it just does not look so awesome ;). If you are not sure which 3D printer to buy or use we can recommend [Prusa i3 MK2S](https://www.prusa3d.com/#our-printer) - we have designed and printed the case on this one.

### Instructions

> No soldering skills or any kind of nuts is required to assemble this Tentacle

1. Download the 3D printable [open source case for Anemone Display Tentacle](#) from Thingiverse.
2. 3D print it *(detailed instructions how to print it are on the Thingiverse link in step 1.)*
3. Assemble the 3D printed case - it comes in 3 parts.
   1. First you need to put the bottom frame on the breadboard. The frame should put mounted from the top to the breadboard. Whole Display Tentacle will stand on the breadboard. If your breadboard has a two-sided sticky tape on the bottom, the whole Tentacle can be sticked by it eg. to a wall.
   2. Then mount your NodeMCU v2 onto the breadboard.
   3. Then you should plug the i2c pins of the OLED display to the breadboard with 4 jumper cables.
   4. Then you should mount the walls part to the bottom part with NodeMCU v2
   5. Then insert the OLED display to the front of the walls part. Align the cable nicelly.
   6. As a last step put the top cover to the walls part.
4. Follow the instructions on your Tentacle detail page in the Anemone Dashboard where is described how the generated `.ino` sketch files should be uploaded.

## How to use

Display Tentacle is directly supported by the Anemone IoT Platform. When adding a Tentacle, select a `Display` as its type. *Mr. Cloud* will generate a sketch which can be used to program the *NodeMCU v2* device accordingly. Instructions how to program the device will be shown on your Tentacle detail page together with a button to download the generated sketch `.ino` file.

> The generated `.ino` file uses the well known *Arduino Ecosystem*.

You can use the `Serial Monitor` in the *Arduino IDE* to debug the Tentacle - the Tentacle is writing there what it is doing.

| ![Display Tentacle](/images/display_tentacle.png) | ![Display Tentacle Back](/images/display_tentacle_back.png) |

[<i class="fa fa-arrow-left" aria-hidden="true"></i> Previous chapter: Devices / Button](/devices/button) | [Next chapter: Devices / BigClown Base <i class="fa fa-arrow-right" aria-hidden="true"></i>](/devices/bc_base)

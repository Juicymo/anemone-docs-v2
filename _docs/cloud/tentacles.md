---
title: Tentacles
category: Cloud
order: 3
---

## What is a Tentacle?

*Tentacle* is how Anemone Platform calls open hardware devices which are connected to it.

> In the end, a fully grown *Anemone* has a lot of cute *Tentacles*, right? ;)

## Supported Tentacles

Anemone platform currently supports two open hardware devices based on [nodeMCU v2](https://www.seeedstudio.com/NodeMCU-v2-Lua-based-ESP8266-development-kit-p-2415.html) by default (we call them **Tentacles**). But *any open hardware device which is capable of using MQTT* can be connected to the Anemone Platform.

| ![Button Tentacle](/images/button_tentacle_small.png) | ![Display Tentacle](/images/display_tentacle_small.png) |


Right now two low-cost hobby Tentacles based on [nodeMCU v2](https://www.seeedstudio.com/NodeMCU-v2-Lua-based-ESP8266-development-kit-p-2415.html) are supported - a [*Button*](/devices/button) and [*Display*](/devices/display).

> Support for an industrial quality devices from the [BigClown family](https://www.bigclown.com/) is coming soon.

### Button Tentacle

#### Features
* *Based on [nodeMCU v2](https://www.seeedstudio.com/NodeMCU-v2-Lua-based-ESP8266-development-kit-p-2415.html)*
* Connected via Wi-Fi
* Requires USB Power
* Low-Cost
* Hobby usage

*Button Tentacle* is an open hardware button. It is connected to the Internet via Wi-Fi. It has to be connected to the power via USB cable. Pressing it can trigger action in your [Flow](/cloud/flows).

[More about Button Tentacle <i class="fa fa-arrow-right" aria-hidden="true"></i>](/devices/button)

### Display Tentacle

#### Features
* *Based on [nodeMCU v2](https://www.seeedstudio.com/NodeMCU-v2-Lua-based-ESP8266-development-kit-p-2415.html)*
* Connected via Wi-Fi
* Requires USB Power
* Low-Cost
* Hobby usage

*Display Tentacle* is an open hardware display. It is connected to the Internet via Wi-Fi. It has to be connected to the power via USB cable. It can show some result value from your [Flow](/cloud/flows).

[More about Display Tentacle <i class="fa fa-arrow-right" aria-hidden="true"></i>](/devices/display)

### BigClown (BC) Base Tentacle

#### Features
* *Based on [BigClown Base Station](https://shop.bigclown.com/modules/)*
* Connected via USB, communicates with *Remotes* on 868 MHz Radio
* Requires USB Power
* Industrial quality and usage

> **Support for this Tentacle Coming Soon!** But a cute 3D Printable Case for it can be downloaded right now.

*BigClown Base Tentacle* allows you to read various data and send it to your [Flow](/cloud/flows). It has a modular sensor architecture (sensors in BigClown world are called *Tags*). BigClown Base Tentacle does not have ability to connect itself to the internet *(therefore to the Anemone Cloud)* directly. You will need to connect it to your computer or RaspberryPi via USB cable or wirelessly to the [BigClown USB Dongle](https://shop.bigclown.com/usb-dongle/).

On the other hand *BigClown Base Tentacle* can receive wireless data from the rest of your BigClown network (for example from the [BigClown (BC) Remote Tentacle](#bigclown-bc-remote-tentacle), the [BigClown USB Dongle](https://shop.bigclown.com/usb-dongle/) can be used for that purpose as well).

> BigClown Tentacles are more complex, versatile and robust than the low-cost tentacles based on NodeMCU v2. BigClown Tentacles have industrial quality. But all come for a cost. BigClown Tentacles are also more expensive.

[More about BigClown (BC) Base Tentacle <i class="fa fa-arrow-right" aria-hidden="true"></i>](/devices/bc_base)

### BigClown (BC) Remote Tentacle

#### Features
* *Based on [BigClown Remote Station](https://shop.bigclown.com/modules/)*
* Communicates with *Base* on 868 MHz Radio
* Operated on Battery Power
* Wireless
* Industrial quality and usage

> **Support for this Tentacle Coming Soon!** But a cute 3D Printable Case for it can be downloaded right now.

*BigClown Remote Tentacle* allows you to read various data and send it to your [Flow](/cloud/flows). It has a modular sensor architecture (sensors in BigClown world are called *Tags*). BigClown Remote Tentacle does not have ability to connect itself to the internet *(therefore to the Anemone Cloud)* directly. You will need to connect it wirelessly to the [BigClown Base Tentacle](#bigclown-bc-base-tentacle) or directly to the [BigClown USB Dongle](https://shop.bigclown.com/usb-dongle/).

On the other hand *BigClown Remote Tentacle* is **the ONLY Tentacle which can operate completelly wirelessly**. It can collect data and send them over radio. It is povered by four AAA batteries.

> BigClown Tentacles are more complex, versatile and robust than the low-cost tentacles based on NodeMCU v2. BigClown Tentacles have industrial quality. But all come for a cost. BigClown Tentacles are also more expensive.

[More about BigClown (BC) Remote Tentacle <i class="fa fa-arrow-right" aria-hidden="true"></i>](/devices/bc_remote)

## Tentacle Usage

Usage of a *Tentacle* is very easy:

* For the supported devices the platform will generate all the necessary source code needed to connect the device to a platform and shows a step-by-step instructions how to upload the generated source code to the device.
* For other devices *(not directly supported)*, the generated MQTT credentials can be used to establish MQTT connection with *Anemone Cloud*.

-----

[<i class="fa fa-arrow-left" aria-hidden="true"></i> Previous chapter: Cloud / Flows](/cloud/flows) | [Next chapter: Devices / Button <i class="fa fa-arrow-right" aria-hidden="true"></i>](/devices/button)

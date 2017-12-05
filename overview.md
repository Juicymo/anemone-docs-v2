---
title: Overview
---

Anemone Platform interconnects *open hardware devices* with a *cloud* and *mobile application*.

## Cloud

The cloud (we call it `Mr. Cloud` in the platform terminology) is a place where your applications run.

Anemone application is called a `Flow`. One signed up user can have many flows running in the *Mr. Cloud* at the same time.

Mr. Cloud is a place to where all open hardware devices (we call them `Tentacles`) are connected via *MQTT*. As a user signed up you can have any number of Tentacles connected to your account at the same time.

> You can [sign up](https://www.anemone.cloud/users/sign_up) to the *Mr. Cloud* for free or learn more about the platform at [www.anemone.cloud](https://www.anemone.cloud). Usage of the Anemone platform is completelly **free of charge**.

## Flows

Anemone application is called *a Flow*. Flows run and live in the *Mr. Cloud*.

> Flow is a computer program created using a [flow based programming](https://en.wikipedia.org/wiki/Flow-based_programming).

Every flow consists of one or more `Pipelines`. *Pipeline* is a linear sequence of `Nodes`.

Pipelines can *fork*, but they *cannot be merged*.

Flows have three types of *nodes*:

1. Input Nodes
2. Application Nodes
3. Output Nodes

Flows are event based. This means that every single time when an *input* node is triggered, a `message` is created and then passed through a chain of nodes connected to this *input* node (which we call a *Pipeline*). This happens till a last *node* in a *pipeline* is reached. If the last node is an *output* node, the resulting message is then send to the output device.

> Flows in the Anemone Platform are created and edited online using a `Drag & Drop` and `JavaScript` in a browser in our custom [Flow Editor](/cloud/editor).

Anemone Platform does support multiple different nodes for every type. For example input node can be a *physical button* or *software button in the mobile app*. Application nodes can *send or load data from some API* or be a `JavaScript` funcion. Output node can be a *physical display* on a open hardware device or a *value in the mobile app*.

[More about Flows <i class="fa fa-arrow-right" aria-hidden="true"></i>](/cloud/flows)

## Tentacles

Anemone Platform can be used in a pure software way. But support for physical open hardware devices is present as well.

> Open Hardware device connected to the Anemone Platform is called a `Tentacle`.

Tentacle can be any Open Hardware device with support of MQTT.

Tentacles can be managed in administration of *Mr. Cloud*. One signed in user can have multiple Tentacles in the system. When a Tentacle is added, its MQTT credentials are generated.

Two low cost Tentacles based on the hobby low-cost [nodeMCU v2](https://www.seeedstudio.com/NodeMCU-v2-Lua-based-ESP8266-development-kit-p-2415.html) are supported by default - a [*Button*](/devices/button) and [*Display*](/devices/display).

> Support for an industrial quality devices from the [BigClown family](https://www.bigclown.com/) is coming soon.

[More about Tentacles <i class="fa fa-arrow-right" aria-hidden="true"></i>](/cloud/tentacles)

## Mobile App

Anemone Platform ships with a Mobile App for [iOS](#) and [Android](#) operating systems. The mobile app is called `Mobile Client` in the platform terminology.

*Mobile Client* can be used by a signed in user to access Flows owned by him. User can interact with these flows by triggering input values or actions or by reading output values.

Content and options available in the *Mobile Client* are fully driven by the flow. As such can be configured exclusively in the [Flow Editor](/cloud/editor).

TODO Buttons to download the app from App Stores

## Architecture

-----

[<i class="fa fa-arrow-left" aria-hidden="true"></i> Previous chapter: Welcome](/) | [Next chapter: Cloud / Editor <i class="fa fa-arrow-right" aria-hidden="true"></i>](/cloud/editor)

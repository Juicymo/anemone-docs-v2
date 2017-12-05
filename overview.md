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

From the architecture (technical) point of view, the Anemone IoT Platform works in the following way.

![Anemone Platform Architecture](/images/architecture.svg)

### Mr. Cloud

![Anemone Platform - Mr. Cloud](/images/anemone_mr_cloud.png)

Core of the platform is a web application written in Ruby on Rails. This application is the presentational website, the administration, the API for Mobile Client an MQTT subscriber. This web application is called **Mr. Cloud**.

### Tentacles

![Anemone Platform - Tentacle Icon](/images/anemone_tentacle.png)

Communication with **Tentacles** is performed via MQTT and coordinated by a [mosquitto MQTT broker](https://mosquitto.org/). Tentacles are the physical (hardware) part of the platform. Any hardware device capable of MQTT communication can be used as a Tentacle. We provide additional support for few selected devices. But the platform is entirelly open and it is not limited technically in this way.

### Mobile Client

![Anemone Platform - Mobile Client Icon](/images/anemone_mobile_client.png)

Communication with **Mobile Client** is currently performed via RESTful JSON API. Updates are realized by HTTP pooling - we are aware of this limitation and a new version of the Mobile Client with full support for WebSockets will be realeased soon. Mobile Client is currently a multi-platform mobile application developed in [Unity](https://unity3d.com/) - this is causing many limitations as well, so the upcoming update will be a fully native application for iOS and Android, written in Swift and Kotlin.

### Flows

The parallel **Flow** pipelines execution is driven by a *background job processing*. We schedule a background job for processing one pipeline. When a fork is required, new job for a forked pipeline is scheduled. Whole system is running on multiple workers which means that a true paralelism can be achieved.

The **Flow Editor** is a SPA (Single Page Web Application) written in JavaScript. It is connected to Mr. Cloud via RESTful JSON API and WebSockets. The Flow Editor is currently written in jQuery. A complete refactoring to Angular is planned in future.

-----

[<i class="fa fa-arrow-left" aria-hidden="true"></i> Previous chapter: Welcome](/) | [Next chapter: Cloud / Editor <i class="fa fa-arrow-right" aria-hidden="true"></i>](/cloud/editor)

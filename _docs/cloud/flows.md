---
title: Flows
category: Cloud
order: 2
---

Flows are designed in the [Flow Editor](/cloud/editor).

## How it works

The principle and architecture of Flows is decribed in the [Pipelines & Nodes](/cloud/editor#pipelines) section of the [Flow Editor documentation](/cloud/editor).

## Example Flows

We have prepared 4 example flows which should introduce you to the features of the platform.

### Shopping Button

#### Tentacles
* *Uses **Button Tentacle***

#### APIs
* *Uses **Shopping List** Endpoint from CSAS WebAPI*

Do you know Amazon Dash Buttons and how users love them? We created our own open-source button for your shopping list. Try it and use it as an inspiration for your business.

[More about Shopping Button Flow <i class="fa fa-arrow-right" aria-hidden="true"></i>](/examples/shopping_button)

### Personal Finances

#### Tentacles
* *Uses **Display Tentacle***

#### APIs
* *Uses **Account Balance** Endpoint from CSAS WebAPI secured by OAuth*

What is your current balance? How much money do you need to save for a car? Connect Display Tentacle with WebAPI from the largest Czech bank Česká spořitelna. Your banking information can be displayed for example in garage.

[More about Personal Finances Flow <i class="fa fa-arrow-right" aria-hidden="true"></i>](/examples/personal_finances)

### Minimal Flow

#### Tentacles
* *Does not need any hardware*

#### APIs
* *Does not need any API*

Minimal Flow demonstrates the most basic flow which can be created. When message is triggered by the Trigger node, a value is logged into a console. This flow does not require any hardware (tentacles) to function.

[More about Minimal Flow <i class="fa fa-arrow-right" aria-hidden="true"></i>](/examples/minimal_flow)

### Advanced Example

#### Tentacles
* *Uses **Button Tentacle** and **Display Tentacle***

#### APIs
* *Does not need any API*

Advanced Example demonstrates how a Button and Display can be used together. When a button is pressed a current time from server is displayed on the display.

[More about Advanced Example <i class="fa fa-arrow-right" aria-hidden="true"></i>](/examples/advanced_example)

-----

[<i class="fa fa-arrow-left" aria-hidden="true"></i> Previous chapter: Cloud / Editor](/cloud/editor) | [Next chapter: Cloud / Tentacles <i class="fa fa-arrow-right" aria-hidden="true"></i>](/cloud/tentacles)

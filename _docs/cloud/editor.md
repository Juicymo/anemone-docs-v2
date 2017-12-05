---
title: Editor
category: Cloud
order: 1
---

![Anemone Flow Editor](/images/editor.png)

## Flows

*Anemone Flow Editor* is an online environment where Anemone Flows can be created and adjusted. Here what is called *Anemone Application* are designed.

Anemone Flow Editor has two main components. The larger area on the left is the editor itself. Here the open flow can be adjusted.

The smaller area on the right are logs. On the top is a **Console Log** where send to the *Console Output Nodes* from flow are shown. On the bottom is a **Flow Log** which shows usefull information about the flow - like when the flow is deployed or when some issues or errors are detected.

> Every flow has to be *deployed* by the green **"Deploy"** button in the top right corner of the flow editor before it can be used.

## Areas

Every flow has three areas (from the left to right):

- Input
- App
- Output

These areas are shown as columns in the editor component.

**Input area** is where *input* nodes of the flow are. **Output area** is where the *output* nodes of the flow are. **App area** in the middle is where the functional nodes which form the **Anemone Application** are.

> This means that *a flow* consists of **Anemone Application** (defined by a set of *App Nodes*) and set of *Input Nodes* and *Output Nodes*.

## Pipelines

![Anemone Flow Pipeline](/images/pipeline.png)

Every flow is divided into individual **Pipelines**. Pipeline is a sequence of *Nodes*.

Data (we call them *messages*) are passed from the left part of the pipeline to the right. That is why the input of the flow is on the left and output on the right.

Pipelines **can be forked**, but they **cannot be merged**.

> This means that the *Flow* is not a *graph*, but a *tree* in terms of data structures.

Every Pipeline is processed *in parallel* and *independently* to the others. Every pipeline has to start in an *Input Node*, but it does not need to exit in *Output Node*.

There is no limitation in the amount of Nodes in one Pipeline. But as well as in any [flow based programming](https://en.wikipedia.org/wiki/Flow-based_programming) environment things will go really crazy for human perception when amount of items in a flow (or in a graph) will go past 60. We were perfectly OK with something like 5 Nodes in a Pipeline in our experiments.

> Connections between nodes in the editor are made with *drag & drop*.

## Nodes

![Anemone Flow Node](/images/node.png)

There are three types of **Nodes**. *Input*, *App* and *Output*. Every *node* can be configured by double clicking on it.

> Nodes can be **added** to the Flow by *dragging* them out of the *Add XXX Node* window. The window for adding a Node will appear after pressing any of the *+ XXX Node* buttons (where *XXX* is on of the *Input*, *App* or *Output*).

### Input Nodes

Input nodes are **triggering messages**. They have to be at the beginning of every *Pipeline*.

![Anemone Input Nodes](/images/input_nodes.png)

There are 4 different input nodes:

#### Device Input

Device Input node will load data from a selected Tentacle with a *data input capability* (eg. like a [Button Tentacle](/devices/button)).

#### Trigger

Trigger node contains a software button which can be used from the Flow Editor. The Trigger node emits a message every time the button is pressed.

Trigger node sends a current timestamp, but the message value can be configured.

> This node is usefull for debugging a flow or for testing it while designing.

#### Timer

Timer node is very similar to *Trigger* node, the only difference is that the configured message is emitted every based on a selected time interval.

The time interval can be configured.

#### Mobile Client Input

Mobile Client Input node will load data from a Mobile Client application from the selected input component or button.

### App Nodes

App nodes define the **application logic**. They are in the middle or at the end of a *Pipeline*.

![Anemone App Nodes](/images/app_nodes.png)

There are 3 different app nodes *(at this moment, in the `v2` of Anemone Platform)*:

#### JS Function

JS Function node allows you to write a piece of code in the [JavaScript](https://www.w3schools.com/js/) programming language. Purpose of this code is to manipulate or adjust the passing message.

The JavaScript code you can write will be called as a function. It will get a variable called `msg`, where the received message is stored. The datatype of the passed `msg` variable is a *JavaScript Object*.

You can freely adjust the individual properties of the `msg` object.

Your JavaScript code should be always ended by the following statement where your adjusted `msg` will be returned for further processing:

```javascript
return msg;
```

The most important property of the `msg` object is `payload`. The value of `payload` property contains the content of the message. You can adjust it to adjust the content of the message:

```javascript
msg.payload = 'Hello World';
return msg;
```

Every JS Function node has a name.

> Console nodes *(described below)* by default show the `payload` property of the message *(but they can be configured to behave differently)*.

You can add more properties to the `msg` object if needed, but they can be ignored by some nodes. All nodes rely on existence of the `payload` property in the message.

You can theoreticaly remove properties from the `msg` object, but to do so is not recommended. You should do that only when you know exactly what you are doing.

> You should write very small and quick JS Function nodes and perform only easy tasks in them in order to maintain performance of your Flow.

#### Add To Shopping List

Add To Shopping List node allows you to store data to a shopping list. This node communicates with the [CSAS WebAPI](https://developers.csas.cz/) **Shopping List Endpoint**.

The result of the interaction (of the API call) is returned as new message. This allows you to interact to it in a required way.

Authentication is done by API token.

> You can explore related example flow [Shopping Button](/examples/shopping_button)

#### Load Account Balance

Load Account Balance node allows you to load account balance from the [CSAS WebAPI](https://developers.csas.cz/) **Account Balance Endpoint**.

The result of the interaction (of the API call) is returned as new message. This allows you to interact to it in a required way.

Authentication is done by OAuth. You can setup the OAuth WebAPI authentication on your [Dashboard](https://www.anemone.cloud/dashboard) by pressing the *"Link your profile with CSAS WebAPI"* button. **All flows owned by one Anemone Platform user share the OAuth identity to CSAS WebAPI**.

> You can explore related example flow [Personal Finances](/examples/personal_finances)

### Output Nodes

Output nodes allows **sending of data to Tentacles or Mobile Client**. They can be at the end of a *Pipeline*.

![Anemone Output Nodes](/images/output_nodes.png)

There are 3 different output nodes:

#### Device Output

Device Output node sends data to a selected Tentacle with a *data output capability* (eg. like a [Display Tentacle](/devices/display)).

#### Console

All data send to the Console node are shown in the **Console Log** window on the right side of the *Flow Editor*.

More than one Console node can be used at the same time. Every *Console* node can have different name. The *Console* node name is used as a prefix in the *Console Log* window.

In configuration of a Console node can be specified which property of received message should be shown. By default the `payload` property is used.

> Console nodes are very useful for debugging of your flow.

#### Mobile Client Output

Mobile Client Output node will send data to a Mobile Client application to the selected output component.

## Console

On the right side of Flow Editor is a *logs area*. It consists of two windows.

Window at the top is labeled *Console Log* and in this window messages from all Console nodes are shown.

Window in the bottom part of the logs area is called *Flow Log*. Here important information about the flow are shown. Both log windows are created mainly for debugging and introspection purposes.

> Both logs windows have a little *Clear* button in the top right corner. This button will clear the window so you can remove old logs easily.


-----

[<i class="fa fa-arrow-left" aria-hidden="true"></i> Previous chapter: Overview](/overview) | [Next chapter: Cloud / Flows <i class="fa fa-arrow-right" aria-hidden="true"></i>](/cloud/flows)

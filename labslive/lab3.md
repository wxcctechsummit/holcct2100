---
title: "Lab 3: IVR and Contact Routing"
---

# Table of Contents
- [Part 1: Setup a Simple Flow and make a test call](#part-1-setup-a-simple-flow-and-make-a-test-call)
  * [1. Configure and Publish the first flow](#1-configure-and-publish-the-flow)
  * [2. Verify your inbound numbers are correctly setup on Calling](#2-verify-your-inbound-numbers-are-correctly-setup-on-calling)
  * [3. Create an inbound Voice Entry Point and Voice Queue](#3-create-an-inbound-voice-entry-point-and-voice-queue)
  * [4. Verify the Audio Prompts, Create the Entry Point flow.](#4-verify-the-audio-prompts-create-the-entry-point-flow)
  * [5. Configure and Publish the flow](#5-configure-and-publish-the-flow)
  * [6. Configure the Entry Point Routing Strategy](#6-configure-the-entry-point-routing-strategy)
  * [7. Configure the Queue Routing Strategy](#7-configure-the-queue-routing-strategy)
  * [8. Make a test call](#8-make-a-test-call)
- [Part 2: Adding Menu and Queue treatment to the call](#part-2-adding-menu-and-queue-treatment-to-the-call)


# Introduction

## Lab Objective

- This lab is designed to ensure you are able to configure a voice contact end to end and receive it on the agent desktop.
- The lab will also contain multiple exercises on flow designer to make you comfortable with the Webex Contact Center Flow Designer and the overall Contact Routing configuration.

## Pre-requisite
- WebEx Calling App installed for Agent installed on your laptop.
- Supervisor's WebEx Calling App installed on your mobile phone.

**Links**
> Control hub: **[https://admin.webex.com](https://admin.webex.com){:target="_blank"}**\
> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}**\
> Desktop: **[https://desktop.wxcc-us1.cisco.com](https://desktop.wxcc-us1.cisco.com){:target="_blank"}**


## Part 1: Setup a Simple Flow and make a test call

<iframe width="560" height="315" src="https://youtu.be/embed/aCJTdOW4uaE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 1. Configure and Publish the first flow
- Configure the flow `flow_wxcclab` with a Play prompt - welcome message and End node.
- Verify and publish the flow.

### 2. Create an inbound Voice Entry Point
- On the Portal create an inbound voice entry point `EP_voice_wxcclab` (Provisioning > Entry Point)
- Map the DN from Control Hub - that is assigned to Wx Calling - on the Entry Point Mappings page. (Proivisioning > Entry Point Mappings). Map the DN to `EP_voice_wxcclab`


### 3. Create an inbound Voice Entry Point and Voice Queue
- Login to Portal and create an inbound voice entry point and voice queue. (Provisioning > Entry Point / Queue). Create `EP_voice_wxcclab` and `Q_voice_wxcclab` respectively.

### 4. Verify the Audio Prompts, Create the Entry Point flow.
- The audio prompts required for the script build out are wav files. The whole bundle of wav files [can be found here](https://cisco.box.com/s/njmhdrho38mbohoqlc7iznkj74bgk7tv){:target="_blank"}.
- You may listen to the files to get an idea of the kind of flows being constructed in the later labs.
- To create a flow and have these wav files ready for use, ensure that these prompt files are already uploaded to the org.
- To upload the audio files, Go to  Routing Strategy (from Portal) > Resources > Audio Files and ensure that the audio files are uploaded. (Browse > New > Upload the files)
- Then, you can go to flow to create the flow. Routing Strategy (from Portal) > Flow > New and create the new flow as described in the video above.


### 1. Configure and Publish the flow
- Configure the flow `flow_wxcclab` with a Play prompt - welcome message and queue block and play music block.
- Configure the Queue Block to `Q_voice_wxcclab`. Map the queue inside of the queue block.
- Configure the event flow under the queue - ensure they have end flow steps.
- Configure the play music to loop, and start 0, end 120 to play 2 minutes of music.
- Verify and publish the flow.

### 6. Configure the Entry Point Routing Strategy
- Configure the Open 24x7 routing strategy time of day on the Entry Point Routing strategy by selecting it on the Routing Strategies > `EP_voice_wxcclab`.
- Map the flow `flow_wxcclab` you just created in there.

### 7. Configure the Queue Routing Strategy
- Create the Queue routing strategy for `Q_voice_wxcclab` using a 24x7 open queue.
- Map the Team `Team_wxcclab` to the Queue. Your Agent will then login to that team to get the call.

### 8. Make a test call
- Login to the agent desktop into `Team_wxcclab` and go to a ready state.
- Dial the number using your cell. You should hear the welcome prompt and get the call on the agent desktop.

## Part 2: Adding Menu and Queue treatment to the call







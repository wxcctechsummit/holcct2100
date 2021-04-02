---
title: "Lab 3: IVR and Contact Routing"
---

# Table of Contents
- [Part 1: Setup a Simple Flow and make a test call](#part-1-setup-a-simple-flow-and-make-a-test-call)
  * [1. Configure and Publish the first flow](#1-configure-and-publish-the-flow)
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

<iframe width="560" height="315" src="https://www.youtube.com/embed/aCJTdOW4uaE" title="WxCC Lab #3 IVR & Call Routing.1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 1. Configure and Publish the first flow
- Create a new flow `MyFirstFlow_<podId>` where PodId is your unique pod number.
- Add play message step and configure it with `0_welcome.wav` prompt. 
- Finish the flow with EndFlow block.
- Verify and publish the flow.

### 2. Create an inbound Voice Entry Point and map a DN

<iframe width="560" height="315" src="https://www.youtube.com/embed/u1GDs_-YYK4" title="WxCC Lab #3 IVR & Call Routing.2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- On the Portal create an inbound voice entry point `EP_voice_<podId>` (Provisioning > Entry Point)
- Map the external number on the Entry Point Mappings page. (Proivisioning > Entry Point Mappings). Map the DN to `EP_voice_<podId>`. The DN is already added on Control Hub.

### 3. Configure the Entry Point Routing Strategy

<iframe width="560" height="315" src="https://www.youtube.com/embed/3lrVvKLvvLc" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- Configure the Open 24x7 routing strategy time of day on the Entry Point Routing strategy by selecting it on the Routing Strategies > `EP_voice_<podId>`.
- Map the flow `MyFirstFlow_<podId>`.

### 4. Make a test call
- Login to the agent desktop into `Team_wxcclab` and go to a ready state. Login agent WebEx Calling application.
- Login to the supervisor WebEx Calling app on your mobile.
- From supervisor's WebEx Calling app, dial the number you associated with EP. You should hear the welcome prompt and then silence.

**Good to Know!**: The call is not dropped, as we use EndFlow block which finishes the flow but does not disconnect the call.

- Modify `MyFirstFlow_<podId>` and replace EndFlow with Disconnect node from CallHandling section. Publish the flow.
- Place a test call again. The call should be disconnected after the welcome prompt.


## Part 2: Adding Queue treatment


-------
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







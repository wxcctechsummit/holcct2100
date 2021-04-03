---
title: "Lab 3: IVR and Contact Routing"
---

# Table of Contents
- [Part 1: Setup a Simple Flow and make a test call](#part-1-setup-a-simple-flow-and-make-a-test-call)
  * [1. Configure and Publish the first flow](#1-configure-and-publish-the-flow)
  * [2. Create an inbound Voice Entry Point and map a DN](#2-create-an-inbound-voice-entry-point-and-map-a-dn)
  * [3. Configure the Entry Point Routing Strategy](#3-configure-the-entry-point-routing-strategy)
  * [4. Make a test call](#4-make-a-test-call)
- [Part 2: Adding Menu and Queue treatment](#part-2-adding-menu-and-queue-treatment)
  * [1. Upload New Prompts](#1-upload-new-prompts)
  * [2. Create Queue](#2-create-queue)
  * [3. Add Menu and Queue treatment to the flow](#3-add-menu-and-queue-treatment-to-the-flow)
  * [4. Make a test call](#4-make-a-test-call)



# Introduction

## Lab Objective

- This lab is designed to ensure you are able to configure a voice contact end to end and receive it on the agent desktop.
- The lab will also contain multiple exercises on flow designer to make you comfortable with the Webex Contact Center Flow Designer and the overall Contact Routing configuration.

## Pre-requisites
- WebEx Calling App installed for Agent installed on your laptop.
- Supervisor's WebEx Calling App installed on your mobile phone.

**Links**
> Control hub: **[https://admin.webex.com](https://admin.webex.com){:target="_blank"}**\
> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}**\
> Desktop: **[https://desktop.wxcc-us1.cisco.com](https://desktop.wxcc-us1.cisco.com){:target="_blank"}**


## Part 1: Setup a Simple Flow and make a test call

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/aCJTdOW4uaE?rel=0" title="WxCC Lab #3 IVR & Call Routing1.1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 1. Configure and Publish the first flow
- Create a new flow `MyFirstFlow_<podId>` where PodId is your unique pod number.
- Add play message step and configure it with `0_welcome.wav` prompt. 
- Finish the flow with EndFlow block.
- Verify and publish the flow.

### 2. Create an inbound Voice Entry Point and map a DN

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/u1GDs_-YYK4?rel=0" title="WxCC Lab #3 IVR & Call Routing1.2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- On the Portal create an inbound voice entry point `EP_voice_<podId>` (Provisioning > Entry Point)
- Map the external number on the Entry Point Mappings page. (Proivisioning > Entry Point Mappings). Map the DN to `EP_voice_<podId>`. The DN is already added on Control Hub.

### 3. Configure the Entry Point Routing Strategy

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/3lrVvKLvvLc?rel=0" title="WxCC Lab #3 IVR & Call Routing1.3" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- Configure the Open 24x7 routing strategy time of day on the Entry Point Routing strategy by selecting it on the Routing Strategies > `EP_voice_<podId>`.
- Map the flow `MyFirstFlow_<podId>`.

### 4. Make a test call
- Login to the agent desktop into `Team_wxcclab` and go to a ready state. Login agent WebEx Calling application.
- Login to the supervisor WebEx Calling app on your mobile.
- From supervisor's WebEx Calling app, dial the number you associated with EP. You should hear the welcome prompt and then silence.

**Good to Know!**: The call is not dropped, as we use EndFlow block which finishes the flow but does not disconnect the call.

- Modify `MyFirstFlow_<podId>` and replace EndFlow with Disconnect node from CallHandling section. Publish the flow.
- Place a test call again. The call should be disconnected after the welcome prompt.

[To top of this lab](#table-of-contents)


## Part 2: Adding Menu and Queue treatment

### 1. Upload New Prompts

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/U7OnhQ3ZPRo?rel=0" title="WxCC Lab #3 IVR & Call Routing2.1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- Download new prompts:
   - [Welcome.wav](https://ayankovs-ccp-s3.s3.eu-west-3.amazonaws.com/wcclab_prompts/Welcome.wav){:target="_blank"}
   - [2OptionMenu.wav](https://ayankovs-ccp-s3.s3.eu-west-3.amazonaws.com/wcclab_prompts/2OptionMenu.wav){:target="_blank"}
   - [QueueMusic.wav](https://ayankovs-ccp-s3.s3.eu-west-3.amazonaws.com/wcclab_prompts/QueueMusic.wav){:target="_blank"}

- Upload audio files to WebEx Contact Center.
  Go to  Routing Strategy (from Portal) > Resources > Audio Files. 
  (Browse > New > Upload the files)

### 2. Create Queue
  <iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/PriGepc0XnU?rel=0" title="WxCC Lab #3 IVR & Call Routing2.2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
- Create a voice queue `Q_voice_<podId>`. (Provisioning > Entry Point / Queue > Queue). 
- In Queue Call Distribution assign agent team `Team_wxcclab` to the Queue. Your Agent will then login to that team to get the call.

### 3. Add Menu and Queue treatment to the flow
- Modify `MyFirstFlow_<podId>`:
  - replace a welcome prompt to the new one `Welcome.wav`
  - add Menu step with prompt `2OptionMenu.wav` and configure two options
  - add Queue Contact step and configure it with queue `Q_voice_<podId>`
- Configure the play music to loop, and start 0, end 120 to play 2 minutes of music.
- Verify and publish the flow.

### 4. Make a test call
- Login to the agent desktop into `Team_wxcclab` and go to a ready state.
- Dial the number using your cell. You should hear the welcome prompt and get the call on the agent desktop.

[To top of this lab](#table-of-contents)

## Part 3: Configure Agent Screen-Pop

### 1. Configure Event Flow
- Configure the event flow under the queue - ensure they have end flow steps.

[To top of this lab](#table-of-contents)

------- *in progress, to be deleted later* -----------







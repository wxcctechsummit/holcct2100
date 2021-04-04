 <link rel="shortcut icon" type="image/x-icon" href="../favicon.ico">
---
title: "Lab 3: IVR and Contact Routing"
---

# Table of Contents
- [Part 1: Setup a Simple Flow and make a test call](#part-1-setup-a-simple-flow-and-make-a-test-call)
  * [1. Configure and Publish the first flow](#1-configure-and-publish-the-first-flow)
  * [2. Create an inbound Voice Entry Point and map a DN](#2-create-an-inbound-voice-entry-point-and-map-a-dn)
  * [3. Configure the Entry Point Routing Strategy](#3-configure-the-entry-point-routing-strategy)
  * [4. Make a test call](#4-make-a-test-call)
- [Part 2: Adding Menu and Queue treatment](#part-2-adding-menu-and-queue-treatment)
  * [1. Upload New Prompts](#1-upload-new-prompts)
  * [2. Create Queue](#2-create-queue)
  * [3. Add Menu and Queue treatment to the flow](#3-add-menu-and-queue-treatment-to-the-flow)
  * [4. Make a test call](#4-make-a-test-call)
- [Part 3: Configure Agent Screen Pop](#part-3-configure-agent-screen-pop)
  * [1. Configure Event Flow](#1-configure-event-flow)
  * [2. Make a test call](#2-make-a-test-call)
  * [3. Configure PhoneContactEnded and AgentDisconnected Events](#3-configure-phonecontactended-and-agentdisconnected-events)



# Introduction

## Lab Objective

- This lab is designed to ensure you are able to configure a voice contact end to end and receive it on the agent desktop.
- The lab will also contain multiple exercises on flow designer to make you comfortable with the Webex Contact Center Flow Designer and the overall Contact Routing configuration.

## Pre-requisites
- WebEx Calling App installed for Agent installed on your laptop.
- Supervisor's WebEx Calling App installed on your mobile phone.

## Quick Links
> Control hub: **[https://admin.webex.com](https://admin.webex.com){:target="_blank"}**\
> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}**\
> Agent Desktop: **[https://desktop.wxcc-us1.cisco.com](https://desktop.wxcc-us1.cisco.com){:target="_blank"}**


## Part 1: Setup a Simple Flow and make a test call

### 1. Configure and Publish the first flow
<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/aCJTdOW4uaE?rel=0" title="WxCC Lab #3 IVR & Call Routing1.1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


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

- Login to the agent desktop into `Team1_wxcclab_<ID>` and go to a ready state. Login agent WebEx Calling application.

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

**Note:** Prompts might be already uploaded by previous students. Feel free to delete them and re-upload again.

- Upload audio files to WebEx Contact Center.
  Go to  Routing Strategy (from Portal) > Resources > Audio Files. 
  (Browse > New > Upload the files)

### 2. Create Queue
<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/PriGepc0XnU?rel=0" title="WxCC Lab #3 IVR & Call Routing2.2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


- Create a voice queue `Q_voice_<podId>`. (Provisioning > Entry Point / Queue > Queue). 

- In Queue Call Distribution assign agent team `Team1_wxcclab_<ID>` to the Queue. Your Agent will then login to that team to get the call.

### 3. Add Menu and Queue treatment to the flow
<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/to58MHGUCq0?rel=0" title="WxCC Lab #3 IVR & Call Routing2.3" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


- Modify `MyFirstFlow_<podId>`:
  
  - replace a welcome prompt to the new one `Welcome.wav`
  
  - add Menu step with prompt `2OptionMenu.wav` and configure two options
  
  - add Queue Contact step and configure it with queue `Q_voice_<podId>`

- Configure the play music with `QueueMusic.wav`prompt,  Start Offset `0`, Music Duration `120` to play 2 minutes of music.

- Verify and publish the flow.

### 4. Make a test call

- Login to the agent desktop into `Team1_wxcclab_<ID>` and go to a ready state.

- From supervisor's WebEx Calling app, dial the number. You should hear the new welcome prompt, press `1` get the call on the agent desktop.

- Place more test calls and experiment with different options:
  
  - press `2` - the call should be disconnected
  
  - provide invalid option - the call should be disconnected
  
  - do not provide input - the call should be disconnected after 3 seconds
  
  - change agent status to Idle, and place a test call with option `1` - the call should stay in queue maximum for 2 minutes

[To top of this lab](#table-of-contents)

## Part 3: Configure Agent Screen Pop

### 1. Configure Event Flow
<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/dYyM5GPxG9w?rel=0" title="WxCC Lab #3 IVR & Call Routing3.1" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


- Configure the event flow inside `MyFirstFlow_<podId>`

- On AgentAnswered Event add Screen Pop block and configure it with:
   
   - URL `http://www.google.com/search`
   
   - Key `q`
   
   - Value `{% raw %}{{NewPhoneContact.ANI}}{% endraw %}`

### 2. Make a test call

- Login to the agent desktop into `Team1_wxcclab_<ID>` and go to a ready state.

- From supervisor's WebEx Calling app, dial the number, press `1`  and get the call on the agent desktop.

- New browser tab pops up with a google search for your supervisor's ANI.

### 3. Configure PhoneContactEnded and AgentDisconnected Events

- Modify Event flow and test screen pop on other events `PhoneContactEnded` and `AgentDisconnected`.

[To top of this lab](#table-of-contents)

<script>
function celeButton() {document.body.style.backgroundImage="url('https://media.giphy.com/media/PMV7yRpwGO5y9p3DBx/giphy.gif')";}
function nextLab() {window.location.href = "https://wxcctechsummit.github.io/holcct2100/labslive/lab4.html";}
</script>

<div id="button-row">
<span id="button1" style="text-align: center; display:inline;">
	<button onclick="celeButton()" style="
  text-align: center;
  border-radius: 5px;
  background-color: rgb(0,255,0);
  padding: 10px;">Click To Finish</button>
</span>
<span id="button2" style="text-align: right; display:inline;">
  <button onclick="nextLab()" style="
  text-align: right;
  border-radius: 5px;
  background-color: rgb(0,255,0);
  padding: 10px;">Next Lab 4: Email and Chat Configuration</button>
</span>
</div>









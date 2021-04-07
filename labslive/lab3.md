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
- [Part 4. Configuring Outdial](#part-4-configuring-outdial)
  * [1. Verify/create the Outdial Entry Point and Queue](#1-verifycreate-the-outdial-entry-point-and-queue)
  * [2. Test Outdial](#2-test-outdial)


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


- Create a new flow `MyFirstFlow_<AttendeeId>`.

- Add play message step and configure it with `0_welcome.wav` prompt. 

- Finish the flow with EndFlow block.

- Verify and publish the flow.

### 2. Create an inbound Voice Entry Point and map a DN
<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/u1GDs_-YYK4?rel=0" title="WxCC Lab #3 IVR & Call Routing1.2" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


- On the Portal create an inbound voice entry point `EP_voice_<AttendeeId>` (**_Provisioning > Entry Point_**)

- Map the external number on the Entry Point Mappings page (**_Proivisioning > Entry Point Mappings_**). Map the available DN to your `EP_voice_<AttendeeId>`, the DN is already added on Control Hub.

### 3. Configure the Entry Point Routing Strategy
<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/3lrVvKLvvLc?rel=0" title="WxCC Lab #3 IVR & Call Routing1.3" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


- Configure the Open 24x7 routing strategy time of day on the Entry Point Routing strategy by selecting it on the Routing Strategies > `EP_voice_<AttendeeId>`.

- Map the flow `MyFirstFlow_<AttendeeId>`.

### 4. Make a test call

- Login to the agent desktop into `Team1_wxcclab_<AttendeeId>` and go to a ready state. Login agent WebEx Calling application.

- Login to the supervisor WebEx Calling app on your mobile.

- From supervisor's WebEx Calling app, dial the number you associated with EP. You should hear the welcome prompt and then silence.

**Good to Know!**: The call is not dropped, as we use EndFlow block which finishes the flow but does not disconnect the call.

- Modify `MyFirstFlow_<AttendeeId>` and replace EndFlow with Disconnect node from CallHandling section. Publish the flow.

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


- Create a voice queue `Q_voice_<AttendeeId>`. (Provisioning > Entry Point / Queue > Queue). 

- In Queue Call Distribution assign agent team `Team1_wxcclab_<AttendeeId>` to the Queue. Your Agent will then login to that team to get the call.

### 3. Add Menu and Queue treatment to the flow
<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/to58MHGUCq0?rel=0" title="WxCC Lab #3 IVR & Call Routing2.3" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


- Modify `MyFirstFlow_<AttendeeId>`:
  
  - replace a welcome prompt to the new one `Welcome.wav`
  
  - add Menu step with prompt `2OptionMenu.wav` and configure two options
  
  - add Queue Contact step and configure it with queue `Q_voice_<AttendeeId>`

- Configure the play music with `QueueMusic.wav`prompt,  Start Offset `0`, Music Duration `120` to play 2 minutes of music.

- Verify and publish the flow.

### 4. Make a test call

- Login to the agent desktop into `Team1_wxcclab_<AttendeeId>` and go to a ready state.

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


- Configure the event flow inside `MyFirstFlow_<AttendeeId>`

- On AgentAnswered Event add Screen Pop block and configure it with:
   
   - URL `http://www.google.com/search`
   
   - Key `q`
   
   - Value `{% raw %}{{NewPhoneContact.ANI}}{% endraw %}`

### 2. Make a test call

- Login to the agent desktop into `Team1_wxcclab_<AttendeeId>` and go to a ready state.

- From supervisor's WebEx Calling app, dial the number, press `1`  and get the call on the agent desktop.

- New browser tab pops up with a google search for your supervisor's ANI.

### 3. Configure PhoneContactEnded and AgentDisconnected Events

- Modify Event flow and test screen pop on other events `PhoneContactEnded` and `AgentDisconnected`.

[To top of this lab](#table-of-contents)

## Part 4: Configuring Outdial
> In the following video, all the required steps to configure and test an outbound call are explained. In order to complet it you will need to login in Webex Calling with the corresponding extension number of the agent.

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/555nzckW2Oo?rel=0" title="WxCC Lab #2 Part 5: Configuring Outdial" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 1. Verify/create the Outdial Entry Point and Queue

- Login in the **[Management Portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}**. 

- Navigate to **_Provisioning >  Entry Points/Queues > Outdial Entry Point_**.

- Create a new Outdial Entry Point. Click on `+ New Outdial Entry Point`, set the **_Name_** `EP_Outdial_<ID>`, set any **_Service Level Threshold_**. It will be automatically associated to `Outdial Queue-1`.

- Go to **_Routing Strategy_** and select the created Outdial Entry Point from drop-down list.

- Create a new Routing Strategy by clicking on `+ New Srategy`.

- Configure the outdial entry point routing strategy with the script **`Outdial_EP.js`**. Set **_OutdialQueue_** as `Outdial Queue-1`.

- Ensure the strategy **time of day** setting is correctly **open 24x7** and marked as **_Default_**.

- Go back to the Management Portal. Navigate to **_Provisioning > Outdial ANI_**, create an Outdial ANI `OutdialANI_<ID>` on the setup by mapping it to the existing toll free number.

- Go to **_Provisioning > Agent Profiles_** and edit the one which is assigned with your agent. By default it is called `Agent-Profile`.

- Go to the **_Dial Plan_** tab.

- Configure all the Outdial settings: Outdial Enabled, Outdial Entry Point as `EP_Outdial_<ID>`, Dial Plan Enabled (Any Format) and select the before created Outdial ANI.


### 2. Test Outdial

- Relogin in the **[Agent Desktop](https://desktop.wxcc-us1.cisco.com){:target="_blank"}** for the new agent profile settings to take effect.

- You should now see the **Outdial button enabled** on the **_Horizontal Header_**.

- **Select the Outdial ANI** and test making a call to your **US** cellphone number or to the provided Cisco Public Tollfree number (**+18005536387**).

- You should **receive a call notification** in the Agent Desktop and your Webex Calling application ringing. If the call is established, you have successfully completed this lab.

[To top of this lab](#table-of-contents)

<script>
function mainPage() {window.location.href = "https://wxcctechsummit.github.io/holcct2100/";}
function nextLab() {window.location.href = "https://wxcctechsummit.github.io/holcct2100/labslive/lab4.html";}
</script>

<div id="button-row">
	<button onclick="mainPage()" style="
  border-radius: 5px;
  background-color: rgb(116,191,75);
  padding: 10px;">Go back to Main Page</button>

 <button onclick="nextLab()" style="
  position: absolute;
  right: 200px;
  border-radius: 5px;
  background-color: rgb(116,191,75);
  padding: 10px;">Next Lab 4: Email and Chat Configuration</button>
  
</div>



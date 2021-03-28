---
title: "Lab 3: IVR and Contact Routing"
---

# Table of Contents
- [Part 1: Setup a Simple Flow and make a test call](#part-1-setup-a-simple-flow-and-make-a-test-call)
  * [1. Verify that your users are ready to login](#1-verify-that-your-users-are-ready-to-login)
  * [2. Verify your inbound numbers are correctly setup on Calling](#2-verify-your-inbound-numbers-are-correctly-setup-on-calling)
  * [3. Create an inbound Voice Entry Point and Voice Queue](#3-create-an-inbound-voice-entry-point-and-voice-queue)
  * [4. Verify the Audio Prompts, Create the Entry Point flow.](#4-verify-the-audio-prompts-create-the-entry-point-flow)
  * [5. Configure and Publish the flow](#5-configure-and-publish-the-flow)
  * [6. Configure the Entry Point Routing Strategy](#6-configure-the-entry-point-routing-strategy)
  * [7. Configure the Queue Routing Strategy](#7-configure-the-queue-routing-strategy)
  * [8. Make a test call](#8-make-a-test-call)
- [Part 2: Adding Menu and Queue treatment to the call](#part-2-adding-menu-and-queue-treatment-to-the-call)
  * [1. Copy out the flow and configure the advanced flow](#1-copy-out-the-flow-and-configure-the-advanced-flow)
  * [2. Configure the Queue Treatment loop and Opt Out and Callback steps](#2-configure-the-queue-treatment-loop-and-opt-out-and-callback-steps)
  * [3. Point to the New flow in the Routing Strategy](#3-point-to-the-new-flow-in-the-routing-strategy)
  * [4. Test the end to end flow](#4-test-the-end-to-end-flow)
  * [5. Execute the Callback](#5-execute-the-callback)


# Introduction

## Lab Objective

- This lab is designed to ensure you are able to configure a voice contact end to end and receive it on the agent desktop.

- The lab will also contain multiple exercises on flow designer to make you comfortable with the Webex Contact Center Flow Designer and the overall Contact Routing configuration.

**IVR Prompts:** We will be configuring static prompts for you and pre-uploading them in part 1. You may also keep a copy of the zip file if you want to manually upload them. In the bonus lab, we also share how you can convert these prompts to dynamic TTS prompts using the Text to speech connector configuration available within flow control.  

**Lookups, Advanced Scripting, Screen-pops:** We have chosen specific areas of focus for advanced scripting topics. We have more content shared in the bonus sections on how to get other use cases configured.

## Pre-requisite

Before you begin this lab
>The following video outlines the pre-requisites before beginning the lab.

<iframe width="560" height="315" src="https://www.youtube.com/embed/hO-yCjjLA5o" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

1. Setup Webex Contact Center Button is Clicked and Greyed Out.
2. Users are provisioned on Control hub.
3. Users configured on Control Hub and assigned Licenses.
4. Admins have proper Webex Contact Center license.
5. Synchronize users is clicked.
6. All users visible on Portal > Users and Contact Center Enabled.
7. All Users that need to login to agent desktop are assigned `Site_wxcclab` and `Team_wxcclab` - e.g agent1,super1,agent2,super2,etc. Also All agents are properly assigned Agent Profiles and Multimedia profiles.
8. Control Hub, Portal and Agent Desktop URLs handy.
9. Admin credentials handy for configuration.
10. Agent Credentials handy to Handle contacts.
11. External Number to Route Transfer outs, voice mail within flow : **Cisco Support Helpline -- `+18005536387`**  -- P.S: *This will actually connect you to the live toll free number!*

**Note on Above Prerequisite Configuration**
> Login to `Control Hub` > Users.
- Ensure the agents have the contact center license selected and are properly configured as Contact center enabled on Webex Contact center. 
- Ensure that they have activated the Email and are "Active" on Control Hub. Synchronize users to get any newly activated users.

> Launch Portal to ensure all the users (admins, agents, supervisors) are contact center configured for testing.
- Create a Site : `Site_wxcclab`, `Team_wxcclab`
- Activate the agents to be Contact Center Enabled.
- Associate the Agents to the Site, Team, default Multimedia Profile - `Default_Telephony_Profile`.
- Verify by Launching the Agent Desktop and logging in.

> Participants can choose to download and install the WebEx Calling App for Agents, Admins or Supervisors and make on-net calls.

**Download instructions**

**[https://help.webex.com/en-us/n730ah9/Install-the-Webex-Calling-App](https://help.webex.com/en-us/n730ah9/Install-the-Webex-Calling-App)**

**Links**

> Control hub: **[https://admin.webex.com](https://admin.webex.com)**

> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal)**

> Desktop: **[https://desktop.wxcc-us1.cisco.com](https://desktop.wxcc-us1.cisco.com)**


## Part 1: Setup a Simple Flow and make a test call

<iframe width="560" height="315" src="https://www.youtube.com/embed/52YiWRZJVcM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Quick Links**

> Control hub: **[https://admin.webex.com](https://admin.webex.com)**

> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal)**

> Agent Desktop: **[https://desktop.wxcc-us1.cisco.com](https://desktop.wxcc-us1.cisco.com)**


### 1. Verify that your users are ready to login
- With the steps outlined in the previous lab and recap above, you should now be able to login to the agent desktop.

### 2. Verify your inbound numbers are correctly setup on Calling 
- The inbound Numbers need to be added on Control Hub.
- The telephony option on the location needs to be set to Intelepeer.
- Settings page needs to have Intelepeer configured for subsequent locations created.

### 3. Create an inbound Voice Entry Point and Voice Queue
- Login to Portal and create an inbound voice entry point and voice queue. (Provisioning > Entry Point / Queue). Create `EP_voice_wxcclab` and `Q_voice_wxcclab` respectively.
- Map the DN from Control Hub - that is assigned to Wx Calling - on the Entry Point Mappings page. (Proivisioning > Entry Point Mappings). Map the DN to `EP_voice_wxcclab`

### 4. Verify the Audio Prompts, Create the Entry Point flow.
- The audio prompts required for the script build out are wav files. The whole bundle of wav files [can be found here](https://cisco.box.com/s/njmhdrho38mbohoqlc7iznkj74bgk7tv).
- You may listen to the files to get an idea of the kind of flows being constructed in the later labs.
- To create a flow and have these wav files ready for use, ensure that these prompt files are already uploaded to the org.
- To upload the audio files, Go to  Routing Strategy (from Portal) > Resources > Audio Files and ensure that the audio files are uploaded. (Browse > New > Upload the files)
- Then, you can go to flow to create the flow. Routing Strategy (from Portal) > Flow > New and create the new flow as described in the video above.

### 5. Configure and Publish the flow
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


<iframe width="560" height="315" src="https://www.youtube.com/embed/6KrtAJuX_J0" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Quick Links**

> Control hub: **[https://admin.webex.com](https://admin.webex.com)**

> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal)**

> Desktop: **[https://desktop.wxcc-us1.cisco.com](https://desktop.wxcc-us1.cisco.com)**

### 1. Copy out the flow and configure the advanced flow
- Open the Portal > Routing Strategy > Flow page.
- Copy the existing flow `flow_wxcclab` and edit the copied flow - name it `advanced_flow1_wxcclab`
- Edit the flow to go into flow designer. 
- Ensure that you configure the Menu steps with a 3 option - 2 queue, 1 Blind Transfer step.
- Ensure you configure all the fields in the menu step including the prompts and the entry timeout (requires you to explore all options on the step).
- Ensure you configure all the blind transfer location to Cisco Toll Free :  `+18005536387` --Note: *This will actually connect you to the live toll free number!*

### 2. Configure the Queue Treatment loop and Opt Out and Callback steps
- In Flow Designer - Configure the Queue treatment for the first queue. Use the `queueCounter` variable and configure the Opt out steps including the high volume message and the callback step.
- Configure the voicemail destination to the same external number above.
- Validate the flow and publish it.

### 3. Point to the New flow in the Routing Strategy
- Go to the routing Strategy page > Routing Strategy > `EP_voice_wxcclab`
- Once the flow is published, configure the Entry Point Routing strategy to point to the new flow `advanced_flow1_wxcclab`.

### 4. Test the end to end flow
- Login to the agent desktop and go Idle (Not Ready)
- Test Queue treatment by going not ready on the agent desktop.
- Call the main number on the entry point and go into the queue. You should hear the queue twice and then have an option to leave a callback.
- leave the callback and the call should end.

### 5. Execute the Callback
- Have the agent go ready after you left a callback.
- They should receive the callback call.




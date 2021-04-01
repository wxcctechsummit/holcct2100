---
title: "Lab 6: Bonus section - Facebook Messenger Integration"
---

### Overview of the lab:
This is a bonus section for the participants who has successfully compleated the mandatory part.

## Table of Contents
- [Part 1: Organization admin: set up Facebook account](#Part-1-Organization-admin-set-up-Facebook-account)
- [Part 2: Configure Facebook Connector in WxCC Control Hub](#Part-2-Configure-Facebook-Connector-in-WxCC-Control-Hub)
- [Part 3: Configure Facebook Connector in Management Portal](#Part-3-Configure-Facebook-Connector-in-Management-Portal)
  * [1. Configure Facebook Entrypoint](#1-configure-facebook-entrypoint)
  * [2. Configure Facebook Queue](#2-configure-facebook-queue)
  * [3. Configure EntryPoint Mappings](#3-configure-entrypoint-mappings)
  * [4. Entry point routing strategy creation](#4-entry-point-routing-strategy-creation)
  * [5. Queue routing strategy creation](#5-queue-routing-strategy-creation)
- [Part 4: Testing Facebook Chat to Agent Desktop](#Part-4-testing-facebook-chat-to-agent-desktop)

# Introduction

### Lab Objective

This lab is designed to configure Facebook to integrate in to WxCC.

End customer can initiate queries from provided facebook page to contact center agents.

### Pre-requisite

- You have successfully completed Lab 1 and Lab 2;
- Facebook account along with login credentials;
- Agent account to login to agent desktop;

# Lab Section

## Part 1: Organization admin: set up Facebook account
>The following video provides detailed steps of configuration from the Facebook side. It will show you how to create a new Facebook page and how to collect API data for Facebook integration.
<iframe width="560" height="315" src="https://www.youtube.com/embed/-i07ntBMQ20" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Quick Links**

- Facebook: [http://facebook.com/](http://facebook.com/){:target="_blank"}


### Steps for creating a Facebook page

* Customer/Partner should have an facebook account that can be used for creating new page.

* Login to the [Facebook](http://facebook.com/){:target="_blank"} to create a business page which will be used for your end customers.

* Once logged in, please select Pages tab which is on left side of the facebook home page.

* Now choose "Create New Page" which is on top left corner.

* Provide the information which is required for creating the page as per your business and organisation.

* Upload cover photo and Logo then save.


## Part 2: Configure Facebook Connector in WxCC Control Hub
>The following video outlines how to create a new Facebook Connector in the Control Hub.
<iframe width="560" height="315" src="https://www.youtube.com/embed/nJI4LrL0sJo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Quick Links**

- Control hub: [https://admin.webex.com](https://admin.webex.com){:target="_blank"}


### Steps for creating a new connector in the Control Hub

* Login to the WxCC portal.

* Once logged into the portal, on left side menu expand to see the available tabs. Select Provisioning and launch users.

* Here we will be able to see the available users and option to launch control hub. Select "Cisco Webex Control Hub".

* login to control hub and select "Contact Center" tab.

* Please provide the same username which was used to login to Cisco WxCC portal.

* Once logged-in to control hub, please select "Contact Center" tab.

* Choose Connectors and select "Facebook Messenger"

* Provide Name and choose I do not have a Facebook Page ID and Access Token.

* Proceed with Authentication to get Page ID and Access Token.

* Once Authenticated copy Page ID and Access Token.

* Update these details in WxCC Hontrol Hub.

* Now you should be able to see the newly created Facebook Page in Social Channels.


## Part 3: Configure Facebook Connector in Management Portal
>Here we go through the list of settings which are needed from the Management Portal perspective. 
<iframe width="560" height="315" src="https://www.youtube.com/embed/dibFEv-xv3g" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Quick Links**

- Managment Portal: [https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}


### 1. Configure Facebook Entrypoint

* Login to the WxCC portal.

* Select left side menu, expand to see the available tabs. Select Provisioning and expand Entry Points/Queues, now choose Entry Point.

* Select "New Entry Point".

* Provide the Entry Point Name, Description and Channel type as "Social Channel" and Social Channel type as "Facebook Messenger" and save.


### 2. Configure Facebook Queue

* Select Provisioning and expand Entry Points/Queues, now choose Queue.

* Select "New Queue".

* Provide the Queue Name, Description and Channel type as "Social Channel".

* Now choose "Add Group" and select the required team names to whom these facebook contacts need to be routed.

* Update the Max time in queue and save.


### 3. Configure EntryPoint Mappings

* Select left side menu, expand Provisioning to see the available tabs. Select "Entry Point Mappings".

* Choose Social Messaging and select "New Mapping".

* Select the Connector and choose the one which we have created in Control Hub, then select entry point and save.  

### 4. Entry point routing strategy creation

* Select left side menu, expand to see the available tabs. Select "Routing Strategy"

* Choose newly created facebook Entrypoint.

* Select new Strategy, provide name, start & end date, add the newly create facebook queue then save.


### 5. Queue routing strategy creation

* Now from the routing strategy page, select the ‘queue’ that you created and choose ‘New Strategy’.

* Provide the Queue Name, start & end date, Max Time In Queue.

* 'Add Group' and Select the team to which the contact should be delivered and click save group.

* Now click save to complete Queue routing strategy settings. 


## Part 4: Testing Facebook Chat to Agent Desktop
>The following video will show how to test the configuration. It will demonstrate how to send a message from Facebook page and how it can be managed by agent.
<iframe width="560" height="315" src="https://www.youtube.com/embed/6Y-VNupYLns" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Quick Links**

- Managment Portal: [https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}
- Agent Interface: [https://desktop.wxcc-us1.cisco.com/](https://desktop.wxcc-us1.cisco.com/){:target="_blank"}


### Agent Desktop: Contact offering to an Agent, Acceptance, and closure

* Select left side menu in Wxcc Portal, expand to see the available tabs. Select "Agent Desktop".

* Login to agent desktop, provide agent login DN and choose the team.

* Once the agent goes Available, the facebook contact will be offered to the agent.

* Click "Accept" to handle the contact, after responding close the task.


Congratulations, you have completed the **bonus section**. Well done!!!

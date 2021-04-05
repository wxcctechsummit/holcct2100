---
title: "Bonus Lab 6: Facebook Messenger Integration"
---

### Overview of the lab:
This is a bonus section for the participants who have successfully completed the mandatory part. In this Lab, we will go through the tasks that are required to complete the Facebook integration with WxCC. At the end of the lab, you should be able to get a Facebook message on the agent desktop.

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

- For doing this lab, you must first complete the **[Lab 1](lab1.md)** and **[Lab 2](lab2.md)**:
   - You have the administrator's access to the Control Hub and Tenant Portal.
   - Agent account to login to agent desktop
- You have a Facebook account along with login credentials.

### Quick Links
> Control Hub: **[https://admin.webex.com](https://admin.webex.com){:target="_blank"}**\
> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}**\
> Facebook: **[http://facebook.com/](http://facebook.com/){:target="_blank"}**\
> Agent Interface: **[https://desktop.wxcc-us1.cisco.com/](https://desktop.wxcc-us1.cisco.com/){:target="_blank"}**

# Lab Section

## Part 1: Organization admin: set up Facebook account
>The following video provides detailed steps of configuration from the Facebook side. It will show you how to create a new Facebook page and how to collect API data for Facebook integration.

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/-i07ntBMQ20?rel=0" title="WxCC Lab #6 Part 1: Organization admin: set up Facebook account" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### Steps for creating a Facebook page

- Customer/Partner should have an facebook account that can be used for creating new page.

- Login to the [Facebook](http://facebook.com/){:target="_blank"} to create a business page which will be used for your end customers.

- Once logged in, please select **_Pages_** tab which is on left side of the facebook home page.

- Now choose **_Create New Page_** which is on top left corner.

- Provide the information which is required for creating the page as per your business and organisation.

- Upload cover photo and Logo then **_Save_**.


## Part 2: Configure Facebook Connector in WxCC Control Hub
>The following video outlines how to create a new Facebook Connector in the Control Hub.

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/nJI4LrL0sJo?rel=0" title="WxCC Lab #6 Part 2: Configure Facebook Connector in WxCC Control Hub" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



### Steps for creating a new connector in the Control Hub

- Login to the [Control Hub](https://admin.webex.com){:target="_blank"} with the admin account.

- Navigate **_Contact Center_** tab.

- Choose **_Connectors_** and select **_Facebook Messenger_**.

- Provide Name `FB_Connector_<ID>` and choose **I do not have a Facebook Page ID and Access Token**.

- Proceed with Authentication to get Page ID and Access Token. Click on **_Authenticate with Facebook_**.

- Once Authenticated copy `Facebook Page ID` and `Facebook Page Access Token`.

- Update these details in WxCC Hontrol Hub.

- Now you should be able to see the newly created Facebook Page in **_Social Channels_**.


## Part 3: Configure Facebook Connector in Management Portal
>Here we go through the list of settings which are needed from the Management Portal perspective. 

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/gmi_kPIOixE?rel=0" title="WxCC Lab #6 Part 3: Configure Facebook Connector in Management Portal" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



| **Entity** | **Name**      | 
| ----------- | ----------------- | 
| Facebook Entrypoint        | EP_Facebook_\<ID\>   | 
| Facebook Queue         | Q_Facebook_\<ID\>  | 
| Team1         | Team1\_wxcclab_\<ID\> | 

### 1. Configure Facebook Entrypoint

- Login to the [WxCC portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}.

- Select left side menu, expand to see the available tabs. Select **_Provisioning_** and expand **_Entry Points/Queues_**, now choose **_Entry Point_**.

- Select **_New Entry Point_**.

- Provide the **Entry Point Name** as `EP_Facebook_<ID>`, Channel type as **Social Channel** and Social Channel type as **Facebook Messenger**. Click **_Save_**.


### 2. Configure Facebook Queue

- Select **_Provisioning_** and expand **_Entry Points/Queues_**, now choose **_Queue_**.

- Select **_New Queue_**.

- Provide the **Queue Name** as `Q_Facebook_<ID>`, and Channel type as **Social Channel**.

- Now choose **_Add Group_** and select the required team `Team1_wxcclab_<ID>` to whom these facebook contacts need to be routed.

- Update the **Max time in queue** to 300 sec and click **_Save_**.

### 3. Configure EntryPoint Mappings

- Select left side menu, expand **_Provisioning_** to see the available tabs. Select **_Entry Point Mappings_**.

- Choose Social Messaging and select **_New Mapping_**.

- Select the Connector `FB_Connector_<ID>` and choose the one which we have created in Control Hub, then select entry point `EP_Facebook_<ID>` and **_Save_**.  

### 4. Entry point routing strategy creation

- Select left side menu, expand to see the available tabs. Select **_Routing Strategy_**.

- Choose newly created facebook Entrypoint `EP_Facebook_<ID>`.

- Select **_New Strategy_**, provide your name, start & end date, add the newly create facebook queue `Q_Facebook_<ID>` then **_Save_**.


### 5. Queue routing strategy creation

- Now from the **_Routing Strategy_** page, select the queue `Q_Facebook_<ID>` that you created and choose **_New Strategy_**.

- Provide the your name, start & end date, Max Time In Queue.

- Click on **_Add Group_** and Select the team `Team1_wxcclab_<ID>` to which the contact should be delivered and click save group.

- Now click **_Save_** to complete Queue routing strategy settings. 


## Part 4: Testing Facebook Chat to Agent Desktop
>The following video will show how to test the configuration. It will demonstrate how to send a message from Facebook page and how it can be managed by agent.

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/6Y-VNupYLns?rel=0" title="WxCC Lab #6 Part 4: Testing Facebook Chat to Agent Desktop" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>



### Agent Desktop: Contact offering to an Agent, Acceptance, and closure

- Select left side menu in Wxcc Portal, expand to see the available tabs. Select **_Agent Desktop_**.

- Login to agent desktop with `agent1_<ID>@mailinator.com`, provide agent login Extension `1000` and choose the team `Team1_wxcclab_<ID>`.

- Once the agent goes **Available**, the facebook contact will be offered to the agent.

- Click **_Accept_** to handle the contact, after responding close the task.


## Congratulations, you have completed the **bonus section**. Well done!!!

---
title: "Lab 5: New Supervisor functionality"
---

### Overview of the lab:

In this lab, we will show you the existing dashboards which are available for supervisor in the Management portal. You will learn how to create a custom access right and will get acquainted with the agent logout feature.


# Table of Contents

- [Part 1: Portal's Dashboards](#part-1-Portals-Dashboards) 
  * [1. Management Portal with Supervisor account](#1-management-portal-with-supervisor-account)
  * [2. Portal's dashboards information](#2-portals-dashboards-information)
- [Part 2: Supervisor permissions and remote agent logout](#part-2-Supervisor-permissions-and-remote-agent-logout) 
  * [1. Agent State Data – Realtime dashboard](#1-agent-state-data--realtime-dashboard)
  * [2. Remote Agent Logout](#2-remote-agent-logout)
  * [3. Supervisor’s User Profile](#3-supervisors-user-profile)

# Introduction

### Lab Objective

- This lab is designed to help you to be familiar with the supervisor dashboards of the Management Portal. 
- It demonstrates a new Agent Log out functionality with the latest "Agent State Data - Realtime" dashboard.
- It shows how to customize a user profile setting and define an access rights.
- 
### Pre-requisites

- You have successfully completed Lab 1, Lab 2 and Lab 3;
- Agent account to login to agent desktop.
- Supervisor account to login to Management Portal.

### Quick Links
> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}**\
> Agent Interface: **[https://desktop.wxcc-us1.cisco.com/](https://desktop.wxcc-us1.cisco.com/){:target="_blank"}**

# Lab Section

## Part 1: Portal's Dashboards

>The following video outlines the existing dashboards available to the supervisor in the management portal. Follow the instructions to find out which dashboards are available and what they are for.

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/0NcgneC1UZo?rel=0" title="WxCC Lab #5 Part 1: Portal's Dashboards" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


 
### 1. Management Portal with Supervisor account

- Make sure the agent is logged into the agent interface **[https://desktop.wxcc-us1.cisco.com/](https://desktop.wxcc-us1.cisco.com/){:target="_blank"}** 

- Make the agent **Available** by selecting the appropriate state in the upper left corner.

- Navigate to **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}** in a new browser tab

- Enter the suprvisor’s **Username** which you created in the lab 1.

- Enter the **Password** for the appropriate Username.

### 2. Portal's dashboards information

- Ensure that browser pop up blockers are not blocking the **_Admin Portal_** pop up. The `Entry Point - Site level` dashboard has to be shown on the landing page.

- Make sure there are more than 0 agents listed in the **AVAILABLE AGENTS** field.

- Make a new call to your EP. After starting IVR, you will see this value in the **IN IVR** field.

- Now redirect your call to the queue with the agent. Make sure the agent answered this call. You should see a value of 1 in the **CONNECTED** field. 

- Navigate to the agent desktop, end your call and move your agent back to the **Idle** status. Nobody should be in **Available** status.

- Go back to the portal's dashboard and select the second dashboard `Contact Center Overview - Realtime` in the upper left corner.

- Make a new call to your EP and wait until the call reach a queue.

- Check the new data on the Realtime dashboard. Now, this call will be presented in the table **Contact Details in the Queue**. In addition, the value will increase in the **Longest Contact Currently in Queue** chart.

-  Select the third dashboard `Contact Center Overview - Historical`. You will be able to see the same information but from the historical perspective. By default the informaiton is shown for the last 7 days. Change the **Duration** filter to **This Year** in the upper right corner. 

- Open the help guide by clicking on the supervisor account in the upper right corner and selecting the **Help** option.

## Part 2: Supervisor permissions and remote agent logout

>Here we go through the newly added dashboard. We will learn how to change supervisor permissions and how to manually log out agents by using a supervisor account.

<iframe width="1024" height="576" src="https://www.youtube-nocookie.com/embed/Ij08tvZltlg?rel=0" title="WxCC Lab #5 Part 2: Supervisor permissions and remote agent logout" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 1. Agent State Data – Realtime dashboard 

- Make sure that the agent is logged in.

- Go to the portal's dashboard as a supervisor and select the 4th dashboard `Agent State Data – Realtime` in the upper left corner.

- Now the agent has to be presented in the **Agent State Data** dashboard.

- Manually refresh dashboard data by clicking on **Stop Refresh** button. As the result, the **time since last refresh** will be restarted.

### 2. Remote Agent Logout 

- To log out an agent, click **Sign Out** button in the Action field. Make sure that you receive a notification that the agent has been successfully logged out.
Note: You can log out agents who are in the Available, Idle, or Not Responding. If the agent is in a **Connected** state the Sign Out button will not be available.

- Go to the Agent desktop and verify the agent status. He should receive the notification that the supervisor has signed him out.

| **Entity** | **Name**      | 
| ----------- | ----------------- | 
| User Profiles        | Supervisor Profile Pod\<ID\>   | 
| Supervisor         | supervisor1_\<ID\>@mailinator.com | 

**NOTE:**

Your \<ID\> is provided in the email in the **"Attendee ID"** line.

### 3. Supervisor’s User Profile

- Make sure the agent is logged back into the agent interface. During the agent login select the `Team2_wxcclab_pod<ID>`.

- Navigate to **_Provisioning_** and select **_User Profiles_**.

- Click on dots `...` infront of **_Supervisor Profile_** and select **Copy** option.

- The new **User Profile** page will be presented. Set the **Name** base on your Pod\<ID\> `Supervisor Profile Pod<ID>`.

- In the **User Profile** page click on **Access Rights**.

- In **Teams** field set only team1 `Team1_wxcclab_pod<ID>` and click **Save**.

- Navigate to **_Provisioning_**, select **_Users_** and modify your supervisor account 

- Click on **_Provisioning_** and select **_Users_**

- Infront of the current supervisor `supervisor1_<ID>@mailinator.com` click on `...` , to launch the **_Edit_** view for a particular User configuration.

- Select a created profile `Supervisor Profile Pod<ID>` in the **_User Profile_** drop down list and hit **_Save_**.

- Log out and log back in to apply the new supervisor profile settings.

- Verify that there are no agents in the `Agent State Data – Realtime` dashboard with a new profile.

- Go to the agent desktop and change the team settings. Switch the agent to the team1 `Team1_wxcclab_pod<ID>`

- In the agent dashboard click the **_Stop Refresh_** button and make sure the agent appears.



## Congratulations, you have completed all mandatory labs. If you still have time, you can go through the [Lab 6: Bonus section - Facebook Messenger Integration](lab6.md)


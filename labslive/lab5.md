---
title: "Lab 5: New Supervisor functionality"
---

### Overview of the lab:

In this lab, we will show you the existing dashboards which are available for supervisor in the Management portal. You will learn how to create a custom access right and will get acquainted with the agent logout feature.


# Table of Contents

- [Part 1: Portal's Dashboards](#part-1-Portals-Dashboards) 
* [1. Management Portal with Supervisor accountp](#management-portal-with-supervisor-account)
* [2. Portal's dashboards information](#portals-dashboards-information)
- [Part 2: Supervisor permissions and remote agent logout](#part-2-Supervisor-permissions-and-remote-agent-logout) 


# Introduction

### Lab Objective

- This lab is designed to help you to be familiar with the supervisor dashboards of the Management Portal. 
- It shows how to customize a user profile setting and define limit access rights.
- It demonstrates a new Agent Log out functionality with the latest "Agent State Data - Realtime" dashboard.

### Pre-requisites

- You have successfully completed Lab 1, Lab 2 and Lab 3;
- There is at least one agent logged in to the Agent desktop;
- You have the supervisor's login credentials;


# Lab Section

## Part 1: Portal's Dashboards

>The following video outlines the existing dashboards available to the supervisor in the management portal. Follow the instructions to find out which dashboards are available and what they are for.

<iframe width="560" height="315" src="https://www.youtube.com/embed/0NcgneC1UZo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


**Quick Links**

- Managment Portal: [https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}
- Agent Interface: [https://desktop.wxcc-us1.cisco.com/](https://desktop.wxcc-us1.cisco.com/){:target="_blank"}
 
### 1. Management Portal with Supervisor account
- Make sure the agent is logged into the agent interface **[https://desktop.wxcc-us1.cisco.com/](https://desktop.wxcc-us1.cisco.com/){:target="_blank"}** 
- Make the agent **Available** by selecting the appropriate state in the upper left corner.
- Navigate to **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}** in a new browser tab
- Enter the suprvisor’s **Username** which you created in the lab 1.
- Enter the **Password** for the appropriate Username.

### 2. Portal's dashboards information
- Ensure that browser pop up blockers are not blocking the **_Admin Portal_** pop up. The **Entry Point - Site level** dashboard has to be shown on the landing page.
- Make sure there are more than 0 agents listed in the **AVAILABLE AGENTS** field.
- Make a new call to your EP. After starting IVR, you will see this value in the **IN IVR** field.
- Now redirect your call to the queue with the agent. Make sure the agent answered this call. You should see a value of 1 in the **CONNECTED** field. 
- Navigate to the agent desktop, end your call and move your agent back to the **Idle** status. Nobody should be in **Available** status.
- Go back to the portal's dashboard and select the second dashboard **Contact Center Overview - Realtime** in the upper left corner.
- Make a new call to your EP and wait until the call reach a queue.
- Check the new data on the Realtime dashboard. Now, this call will be presented in the table **Contact Details in the Queue**. In addition, the value will increase in the **Longest Contact Currently in Queue** chart.
-  Select the third dashboard **Contact Center Overview - Historical**. You will be able to see the same information but from the historical perspective. By default the informaiton is shown for the last 7 days. Change the **Duration** filter to **This Year** in the upper right corner. 


## Part 2: Supervisor permissions and remote agent logout

### 1. Supervisor User Profile 
### 2. Agent State Data dashboard for the Agent Logout 

Congratulations, you have completed all mandatory labs. If you still have time, you can go through the advanced section [Lab 6: Advance features](lab6.md)



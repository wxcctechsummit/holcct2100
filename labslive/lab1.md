---
title: "Lab 1: Control Hub And Admin Portal"
---

### Overview of the lab:

In this Lab, we will go through the tasks that are required to complete the general pre-configuration of a tenant. These tasks are to be undertaken by a customer administrator. By following each of the steps, you would have prepped your tenant to begin configuring different services offered by the platform. At the end of the lab, you should be able to login an agent with the configured user extension.

# Table of Contents

- [Part 1: Control Hub User Management Admin Task](#part-3-control-hub-user-management-admin-task)
  * [1. Add an agent and a supervisor users and configure the calling extension](#2-add-an-agent-user-and-configure-the-calling-extension)
  * [2. Optionally, add the rest of the users](#4-add-rest-of-the-users)
- [Part 2: Admin Portal Multimedia Profile, Site and Team Configuration](#part-4-admin-portal-multimedia-profile-site-and-team-configuration)
  * [1. Create a new MultiMedia Profile](#1-create-a-new-multimedia-profile)
  * [2. Create a new Site](#2-create-a-new-site)
  * [3. Create a new Team](#3-create-a-new-team)
- [Part 3: Admin Portal User Configuration](#part-5-admin-portal-user-configuration)
  * [1. Synchronize Webex Contact Center Users](#1-synchronize-webex-contact-center-users)
  * [2. Manage settings for existing user](#2-manage-settings-for-existing-user)

# Introduction

### Lab Objective

- This lab is designed to help you to be familiar with the control hub and admin portal UI. 
- The lab contains multiple exercises on Control Hub and Admin Portal to make you comfortable with the Webex Contact Center application.

### Pre-requisites

- You have an assigned POD ID;
- You have the customer admin login credentials;
- You have the calling DNIS;
- You have the agent's extension number;

# Lab Section

## Part 1: Control Hub User Management Admin Task

>The following video outlines the process to manage different types of users to the Customer tenant. Following the steps, you will add a new agent's user and set the extension. While adding the user, we will see how to select user roles. Also, we will see how to change the user to an administrator for the customer tenant.

<iframe width="560" height="315" src="https://www.youtube.com/embed/-_wP9lwZbCE" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


**Quick Links**

 Control hub: [https://admin.webex.com](https://admin.webex.com)

| **user Role** | **User email**      | **User Extension**                   |
| ----------- | ----------------- | -------------------------------- |
| Agent        | AgentpodX_wxcclab\_<your surname or company name\>   | 1000 |
| Supervisor         | SupervisorpodX_wxcclab\_<your surname or company name\>  | 1001 |
 
### 1. Add an agent and a supervisor users and configure the calling extension

- Navigate to **_Users_**
- Click on **_Manage Users_** button
- Click on **_Manually Add or Modify User_**
- Select **_Next_** in **_Manage Users_** pane.
- Input the **_EmailID_** of the agent and supervisor users and click **_Next_**
- Verify that the **EmailID** is same as the one shared to you and click **_Next_**
- Check **_Webex Teams_** , **_Webex Calling (Enterprise)_** & **_Contact Center_**
- Ensure that the License Type is **_Premium Agent_** and Role is **_Agent_** and click **_Add Users_**
- In the next page, enter the correct **_Extension_** under **_Assign Numbers_**. You can find this in the information already shared with you.
- Click **_Finish_**
- Validate the users by going to [www.mailinator.com](www.mailinator.com). Check the email inbox and follow the instructions to validate the email account.

### 2. Optionally, add the rest of the users

- Please follow the same steps as above to add any extra users that you want to add to the Contact Center.

## Part 2: Admin Portal Multimedia Profile, Site and Team Configuration

>The following video outlines how to access the admin portal and navigate the different configuration menus to create a Site, Team, and Multimedia Profile that will be assigned to each different Contact Center Users. We will also see how to navigate to Admin Portal from Control Hub UI

<iframe width="560" height="315" src="https://www.youtube.com/embed/c8po-wBO7Iw" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


**Quick Links**

Control hub: [https://admin.webex.com](https://admin.webex.com)
Control hub: [https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal)


| **Role** | **Name**      | 
| ----------- | ----------------- | 
| Multimedia Profiles        | MM_Profile_wxcclab_\<your surname or company name\>   | 
| Site         | Site_wxcclab_\<your surname or company name\>  | 
| Team1         | Team_wxcclab_\<your surname or company name\> | 
| Team2         | Team2_wxcclab\_<your surname or company name\>  | 

### 1. Create a new MultiMedia Profile

- Login to Control Hub by accessing [https://admin.webex.com](https://admin.webex.com)
- Enter the admin email id and the password.
- Navigate to **_Contact Center_** Card
- Click on **_Settings_**
- Scroll down to **_Webex Contact Center Management_**
- Click on **_Go to Webex Contact Center Management Portal_**
- Ensure that browser pop up blockers are not blocking the **_Admin Portal_** pop up.
- Click on **_Provisioning_** and select **_Multimedia Profiles_**
- Click on **_+ New Multimedia Profile_** to open Multimedia Profile configuration page.
- Input Name as **_MM_Profile_wxcclab_XXXXX_** and input **_1_** for **_Voice_**, **_3_** for **_Email_** and **_3_** for **_Chat_** and click **_Save_**

### 2. Create a new Site

- Navigate to **_Provisioning_** and select **_Site_**
- Click on **_+ New Site_** button and provide the Name as **_Site_wxcclab_XXXXX_**
- Select **_MM_Profile_wxcclab_XXXXX_** in the **_Multimedia Profile_** drop down and hit **_Save_**

### 3. Create a new Team 1 

- Navigate to **_Provisioning_** and select **_Team_**
- Click on **_+ New Team_**
- Select **_Site_wxcclab_XXXXX_** from the Site drop down
- Input Name as **_Team1_wxcclab_XXXXX_**
- Select **_MM_Profile_wxcclab_XXXXX_** in the **_Multimedia Profile_** drop down
- Select **_Global Layout_** in the **_Desktop Layout_** drop down and hit **_Save_**

### 4. Create a new Team 2

- Please follow the same steps as above to add an extra Team as **_Team2_wxcclab_XXXXX_**

## Part 3: Admin Portal User Configuration

>The following video outlines how to configure the users in Admin Portal that were added first in Control Hub. This is a very critical task from the Contact Center perspective. We also would take a look at how to associate customer-created Site, Team, and Multi-Media Profile with those users. Post this we should be able to successfully login as an agent using any of the users and their associated extension.

<iframe width="560" height="315" src="https://www.youtube.com/embed/MIpJofmfWKc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


**Quick Links**

Control hub: [https://admin.webex.com](https://admin.webex.com)
Control hub: [https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal)

### 1. Synchronize Webex Contact Center Users

- Login to Control Hub by accessing [https://admin.webex.com](https://admin.webex.com)
- Enter the admin email id and the password.
- Navigate to **_Contact Center_** Card
- Click on **_Settings_**
- Click on **_Synchronize Users_**

### 2. Manage settings for existing user

- Scroll down to **_Webex Contact Center Management_**
- Click on **_Go to Webex Contact Center Management Portal_**
- Ensure that browser pop up blockers are not blocking the **_Admin Portal_** pop up
- Click on **_Provisioning_** and select **_Users_**
- Click on **_..._** for the first user, to launch the **_Edit_** view for a particular User configuration
- Ensure that **_Administrator Profile_** is selected in the **_User Profile_** drop down.
- Click on **_Contact Center Enabled_** Toggle to move it to **_On_**
- In the **_Agent Settings_** section, select **_Site_wxcclab_XXXXX_** in the Site drop down
- Click in the **_Teams_** area and select **_Team1_wxcclab_XXXXX_** and **_Team2_wxcclab_XXXXX_**
- Select **_MM_Profile_wxcclab_XXXXX_** in the **_Multimedia Profile_** drop down and hit **_Save_**
- Repeat the same for **_all other users_** by selecting the appropriate profile in the **_User Profile_** drop down

Now you are ready to start the next [Lab 2: Exploring the Agent Desktop](labslive/lab2.md)

Changelog:

| **Version** | **Comments**      | **Author(s)**                    | **Date**    |
| ----------- | ----------------- | -------------------------------- | ----------- |
| 1.0         | Initial Release   | Raghu Krishnan (rakrish2) | 08 Jan 2021 |
| 1.1         | Minor Update   | Dmitry Bokatov (dbokatov) | 25 March 2021 |

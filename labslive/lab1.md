---
title: "Lab 1: Control Hub And Admin Portal"
---

### Overview of the lab:

In this Lab, we will go through the tasks that are required to complete the general pre-configuration of a tenant. These tasks are to be undertaken by a customer administrator. By following each of the steps, you would have prepped your tenant to begin configuring different services offered by the platform. At the end of the lab, you should be able to login an agent with the configured user extension.

# Table of Contents

- [Part 1: Control Hub User Management Admin Task](#part-1-control-hub-user-management-admin-task) 
  * [1. Add an agent and a supervisor users and configure the calling extension](#1-add-an-agent-and-a-supervisor-users-and-configure-the-calling-extension)
  * [2. Optionally, add the rest of the users](#2-optionally-add-the-rest-of-the-users)
- [Part 2: Admin Portal Multimedia Profile, Site and Team Configuration](#part-2-admin-portal-multimedia-profile-site-and-team-configuration)
  * [1. Create a new MultiMedia Profile](#1-create-a-new-multimedia-profile)
  * [2. Create a new Site](#2-create-a-new-site)
  * [3. Create a new Team 1](#3-create-a-new-team-1)
  * [4. Create a new Team 2](#4-create-a-new-team-2)
- [Part 3: Admin Portal User Configuration](#part-3-admin-portal-user-configuration)
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

### Quick Links
> Control hub: **[https://admin.webex.com](https://admin.webex.com){:target="_blank"}**\
> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal){:target="_blank"}**\


# Lab Section

## Part 1: Control Hub User Management Admin Task

>The following video outlines the process to manage different types of users to the Customer tenant. Following the steps, you will add new users and set the extension. While adding the user, we will see how to select user roles. 

<iframe width="560" height="315" src="https://www.youtube.com/embed/LRadvKFIPjA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


| **User Role** | **User email**      | **User Extension**                   |
| ----------- | ----------------- | -------------------------------- |
| Agent        | Agent_wxcclab_pod\<ID\>@mailinator.com   | 1000 |
| Supervisor         | Supervisor_wxcclab_pod\<ID\>@mailinator.com  | 2000 |
 
### 1. Add an agent and a supervisor users and configure the calling extension

* Navigate to **_Users_**

* Click on **_Manage Users_** button

* Click on **_Manually Add or Modify User_**

* Select **_Next_** in **_Manage Users_** pane.

* Input the `EmailID` of the agent and supervisor users and click **_Next_**

* Verify that the **EmailID** is same as in the table above and click **_Next_**

* Check **_Webex Teams_** , **_Webex Calling (Enterprise)_** & **_Contact Center_**

* Ensure that the License Type is **_Premium Agent_** and Role is **_Agent_** and click **_Add Users_**. 

* In the next page, make sure that the **_Location_** is selected under **_Assign Numbers_**. The correct value should be already selected by default.

* In the same page, Enter the correct `Extension` under **_Assign Numbers_**. You can find this in the table above.

* Click **_Finish_**

* Select the supervisor user and modify his role to **_Supervisor_** by clicking on **_Edit_** button.

* Validate the users by going to [https://www.mailinator.com/](https://www.mailinator.com/){:target="_blank"}. Check the emails inbox and follow the email instructions to activate the user account.

### 2. Optionally, add the rest of the users

* Please follow the same steps as above to add any extra users that you want to add to the Contact Center.

## Part 2: Admin Portal Multimedia Profile, Site and Team Configuration

>The following video outlines how to access the admin portal and navigate the different configuration menus to create a Site, Team, and Multimedia Profile that will be assigned to each different Contact Center Users. We will also see how to navigate to Admin Portal from Control Hub UI

<iframe width="560" height="315" src="https://www.youtube.com/embed/_Bdt7WV8DCg" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


| **Entity** | **Name**      | 
| ----------- | ----------------- | 
| Multimedia Profiles        | MM_Profile_wxcclab_pod\<ID\>   | 
| Site         | Site_wxcclab_pod\<ID\>  | 
| Team1         | Team1_wxcclab_pod\<ID\> | 
| Team2         | Team2_wxcclab_pod\<ID\>  | 

### 1. Create a new MultiMedia Profile

* Login to Control Hub by accessing [https://admin.webex.com](https://admin.webex.com){:target="_blank"}

* Enter the admin email id and the password.

* Navigate to **_Contact Center_** Card

* Click on **_Settings_**

* Scroll down to **_Webex Contact Center Management_**

* Click on **_Go to Webex Contact Center Management Portal_**

* Ensure that browser pop up blockers are not blocking the **_Admin Portal_** pop up.

* Click on **_Provisioning_** and select **_Multimedia Profiles_**

* Click on `+` **_New Multimedia Profile_** to open Multimedia Profile configuration page.

* Input Name as `MM_Profile_wxcclab_pod\<ID\>_` and input `1` for **_Voice_**, `3` for **_Chat_**, `3` for **_Email_**, `3` for **_Social Channel_** and click **_Save_**

### 2. Create a new Site

* Navigate to **_Provisioning_** and select **_Site_**

* Click on `+` **_New Site_** button and provide the Name as `Site_wxcclab_pod\<ID\>`

* Select `MM_Profile_wxcclab_pod\<ID\>` in the **_Multimedia Profile_** drop down and hit **_Save_**

### 3. Create a new Team 1 

* Navigate to **_Provisioning_** and select **_Team_**

* Click on `+` **_New Team_**

* Select `Site_wxcclab_pod\<ID\>` from the Site drop down

* Input Name as `Team1_wxcclab_pod\<ID\>`

* Select `MM_Profile_wxcclab_pod\<ID\>` in the **_Multimedia Profile_** drop down

* Select **_Global Layout_** in the **_Desktop Layout_** drop down and hit **_Save_**

### 4. Create a new Team 2

* Please follow the same steps as above to add an extra Team as `Team2_wxcclab_pod\<ID\>`. Later we will use this team to assign a custom Desktop Layout.

## Part 3: Admin Portal User Configuration

>The following video outlines how to configure the users in Admin Portal that were added first in Control Hub. This is a very critical task from the Contact Center perspective. We also would take a look at how to associate customer-created Site, Team, and Multi-Media Profile with those users. Post this we should be able to successfully login as an agent using any of the users and their associated extension.

<iframe width="560" height="315" src="https://www.youtube.com/embed/eUDI-5z0VyQ" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 1. Synchronize Webex Contact Center Users

* Login to Control Hub by accessing [https://admin.webex.com](https://admin.webex.com){:target="_blank"}

* Enter the admin email id and the password.

* Navigate to **_Contact Center_** Card

* Click on **_Settings_**

* Click on `Synchronize Users`

### 2. Manage settings for existing user

- Scroll down to **_Webex Contact Center Management_**

- Click on **_Go to Webex Contact Center Management Portal_**

- Ensure that browser pop up blockers are not blocking the **_Admin Portal_** pop up

- Click on **_Provisioning_** and select **_Users_**

- Click on `...` for the first user, to launch the **_Edit_** view for a particular User configuration

- Ensure that **_Administrator Profile_** is selected in the **_User Profile_** drop down.

- Click on **_Contact Center Enabled_** Toggle to move it to **_On_**

- In the **_Agent Settings_** section, select `Site_wxcclab_pod\<ID\>` in the Site drop down

- Click in the **_Teams_** area and select `Team1_wxcclab_pod\<ID\>` and `Team2_wxcclab_pod\<ID\>`

- Select `MM_Profile_wxcclab_pod\<ID\>` in the **_Multimedia Profile_** drop down and hit **_Save_**

- Repeat the same for **_all other users_** by selecting the appropriate profile in the **_User Profile_** drop down.


## Congratulations, you are now ready to start the next [Lab 2: Exploring the Agent Desktop](lab2.md)



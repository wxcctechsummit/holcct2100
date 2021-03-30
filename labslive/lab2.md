---
title: "Lab 2: New Agent Desktop Experience"
---
<iframe src="https://cisco.app.box.com/embed/s/6gyzv6pmg276f2abgm0vgeeoad7j0jr4?sortColumn=date&view=list" width="500" height="400" frameborder="0" allowfullscreen webkitallowfullscreen msallowfullscreen></iframe>

<iframe src="https://cisco.box.com/v/CiscoLiveLogo" width="500" height="400" frameborder="0" allowfullscreen webkitallowfullscreen msallowfullscreen></iframe>

[Image](https://cisco.box.com/v/CiscoLiveLogo)



  <img src="https://cisco.box.com/s/6gyzv6pmg276f2abgm0vgeeoad7j0jr4">

<p align="center">
  <img src="https://cisco.box.com/s/6gyzv6pmg276f2abgm0vgeeoad7j0jr4">
</p>

<iframe src="https://cisco.box.com/s/6gyzv6pmg276f2abgm0vgeeoad7j0jr4" width="500" height="400" frameborder="0" allowfullscreen webkitallowfullscreen msallowfullscreen></iframe>



### Overview of the lab:
In this Lab, we will explore the different sections and some useful options of the Agent Desktop. You will watch a demo video about Agent Desktop overview and you will configure some options by following the described steps. At the end of the lab, you should be able to know where to find the different features and customize your own desktop layout.


# Table of Contents

- [1. Access to the Agent Desktop](#part-1:-access-to-the-agent-desktop)
- [2. Agent Desktop Overview](#part-2:-agent-desktop-overview)
- [3. Configure the User Profile](#part-3:-configure-the-user-profile)
- [4. Custom Desktop Layout](#part-4:-custom-desktop-layout)


# Introduction

## Lab Objective

The objective of this lab is to **explore the New Agent Desktop**, in order to be familiar with the new structure, learn about recently released features and be able to configure basic functionalities.

## Pre-requisites

For doing this lab, you must first **complete the [Lab 1: Control Hub and Admin Portal](lab2.md)**:
- You have the administrator's access to the Tenant Portal;
- Agent created and configured;
- Agent is part of 2 Teams;
- Webex Calling extensions are assigned to a WxCC user:

# Lab Section

## Part 1: Access to the Agent Desktop

<iframe width="560" height="315" src="https://www.youtube.com/embed/4aKajHZeuLo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 2. Webex Calling

### 2. Login
- Navigate to **[https://desktop.wxcc-us1.cisco.com/](https://desktop.wxcc-us1.cisco.com/)** in a new browser tab
- Enter the agent’s **Username** which you created in the previous lab.
- Enter the **Password** for the appropriate Username
- In the Station Login pane, select **"Extension"** and input the configured number for that user. 
**Note** Please use only Extension for this lab
- Select the **Team1_wxcclab_pod\<ID>**, with default layout. 
- Click **_Submit_**
			
If you are successfully logged in the Agent Desktop you have completed this section and you can continue with the next part!



## Part 2: Agent Desktop Overview

<iframe width="560" height="315" src="https://www.youtube.com/embed/6PhY8Wl_8Rw" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 1. Agent Desktop sections

![Image1](AgentDesktopOverview.png)

The Agent Desktop is divided in 6 sections. In the image above you can see a general view of the Agent Desktop and where each section is located. We explain them all shortly:
1. **Task List**: When a request is routed to your queue and you are _Available_, a new request appears in your Task List pane. You must accept the requests to start communication with the customer.
2. **Horizontal Header**: Basic functionalities such as: Title and logo, Agent availability state, Notification Center, Outbound Call and User Profile. We will explain more in detail some User Profile options in the next section of the lab.
3. **Interaction Control**: When you accept a voice call (inbound or outbound), by default, the Interaction Control pane is expanded. This pane includes: customer information (CAD variables), timers (for example: connected and call on hold time) and call control buttons (Record, Hold, Transfer...).
4. **Auxiliary Information**: This section only appears when you accept an email, chat or social messaging conversation request, not for Voice requests. The center pane displays details based on your selection of the contact card in the Task List panel.
5. **Agent Interaction History**: You can view your previous communications with a customer across all the channels (voice, email, chat, and social) in this pane. The pane displays details for the last 24 hours.
6. **Navigation bar**: By default you can find the following icons here: Home, Agent Performance Statistics and Help. However, you can customize it and add some additional icons and widgets.





### 2. Verification of understanding

Finally, in order to make sure that you have understood the basic concepts, we ask you to **complete the following tasks**:
   * **Verify that Agent can see reports**
   * **Download the Agent Dekstop User Guide**


 


## Part 3: Configure the User Profile


<iframe width="560" height="315" src="https://www.youtube.com/embed/3ZrPeIBE-HA" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

### 1. Change Notifications setting and volume
- Scroll down to **_User Settings_**
- Click on **_Notification Settings_**
- **Toggle** any of the 3 options to **enable or disable** different notifications
- Move the **Sound Volume** toggle bar
- You'll test this in the next lab.
- Check this when you receive a notification
		
### 2. Switch to Dark Mode
- Go again under **_User Settings_**
- Toggle the **_Switch to Dark Mode_** button to enable or disable it
		
### 3. See the list of the keyboard shortcuts
- Scroll down to **_Help_**
- Click on **_Keyboard Shortcuts_** or press **Ctrl+Alt+F**
- **See the list** of the keyboard shortcuts
- Find and test the combination to make the Agent status **_'Available'_**
		
### 4. Download Error Report
- Scroll down to **_Help_**
- Click on **_Keyboard Shortcuts_** or press **Ctrl+Shift+2**
- Find the downloaded **error reports** file in your machine



## Part 4: Custom Desktop Layout

<iframe width="560" height="315" src="https://www.youtube.com/embed/Olrifma7Khc" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>


### 1. Download default desktop Layout
- Login to **[https://portal.wxcc-us1.cisco.com](https://portal.wxcc-us1.cisco.com)** with admin credentials​
- Navigate to **_Provisioning_** –> _**Desktop Layout**_​
- Click on ellipses **(…)** of Global Layout and select **_Edit_** ​
- Click on **_Download_** button to download the **Default Desktop Layout.json** file

### 2. Customize default desktop layout with logo and title
- Open the **Default Desktop Layout.json** file with any text editor (e.g. Notepad or Sublime text)​
- Modify the **_appTitle_** key value with your company name in order to change Agent Desktop title
- Modify the **_logo_** key value with your company logo URL or use this CiscoLive logo url: **https://ayankovs-ccp-s3.s3.eu-west-3.amazonaws.com/CiscoLiveLogo.jpg**
- **_Save As_** the JSON file with a distinguishable name

### 3. Upload the custom desktop layout 
- Go again to **_Desktop Layout_** module in the **[Tenant Portal](https://portal.wxcc-us1.cisco.com)**
- Click on **_New Layout_**
- Provide any preferable **name and description** 
- Select **Team2_wxcclab_pod\<ID>** as Team		
- Click **_Upload_** button to upload the modified JSON file​		
- Click **_Save_** button to apply the layout.

### 4. Associate the custom desktop layou to other team
- Go to the **_Team_** module
- Click on ellipses **(…)** of **Team2_wxcclab_pod\<ID>** and select **_Edit_**
- Modify the **_Desktop Layout_** field with the new Desktop Layout created before


### 5. Verify the new custom desktop layout
- Login in the **[Agent Desktop](https://desktop.wxcc-us1.cisco.com/)**
- Open the **_User Profile_** and click on the arrow **'>'** under **_Team_**
- Change the team of the agent to **Team2_wxcclab_pod\<ID>**
- Click on **_Save Team Selection_**
- **Confirm** the changes
- **Wait** some seconds to see the result



## Part 5: Configuring Outdial

<iframe width="560" height="315" src="https://www.youtube.com/embed/UMUM3zJUK7c" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

**Quick Links**

> Control hub: **[https://admin.webex.com](https://admin.webex.com)**

> Portal: **[https://portal.wxcc-us1.cisco.com/portal](https://portal.wxcc-us1.cisco.com/portal)**

> Desktop: **[https://desktop.wxcc-us1.cisco.com](https://desktop.wxcc-us1.cisco.com)**


### 1. Verify/create the Outdial Entry Point and Queue
- Login to Portal > Provisioning > Outdial Entry Point / Outdial Queue.
- Ensure that the system created outdial entry points and queues are present and configure their settings.
- Go to Provisioning > Outdial ANI > Create an Outdial ANI on the setup by mapping it to your existing toll free.
- Go to Provisioning > Agent Profiles > Select the Agent Profile and go to the Dial Plan tab.
- Configure all the Outdial settings on the dial plan.


### 2. Create the Outdial Entry Point Routing Strategy
- Go Routing Strategy > Outdial Entry Point-1 and configure the outdial entry point routing strategy to the script `Outdial_EP.js` which is the system default.
- Ensure the strategy time of day setting is correctly open 24x7 and marked default.

### 3. Create the Outdial Queue Routing Strategy
- Go Routing Strategy > Outdial Queue-1 and configure the outdial queue routing strategy to map to the `Team_wxcclab`.

### 4. Test Outdial
- Logout/login the Agent on the agent desktop for the new agent profile settings to take effect.
- You should see the Outdial button and the agent is now able to make an outdial call.
- Test it by calling your cell or the provided Cisco Public Tollfree -  +18005536387` --Note: *This will actually connect you to the live toll free number!*
- You should have all the connected call features pop on the agent desktop once the call is complete.



Congratulations, you are now ready to start the next [Lab 3: IVR and Contact Routing](lab3.md)


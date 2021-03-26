# Lab 2: New Agent Desktop Experience

Video example

<iframe width="560" height="315" src="/videos/Lab2_Section1.html" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Table of Contents

- [1. Access to the Agent Desktop](#1-access-to-the-agent-desktop)
- [2. Agent Desktop Overview](#2-agent-desktop-overview)
- [3. Configure the User Profile](#3-configure-the-user-profile)
- [4. Custom Desktop Layout](#4-custom-desktop-layout)


# Lab Objective

The objective of this lab is to **explore the New Agent Desktop**, in order to be familiar with the its new structure, learn about recently released features and be able to configure basic options.

# Pre-requisites

For doing this lab, you need first to **complete the previous Lab 1: Control Hub and Admin Portal**, so you need to have already done:
* Administrator access to the Tenant Portal
* Agent created and configured
* Agent is part of 2 Teams
* User is assigned to a Webex Calling extension


# 1. Access to the Agent Desktop

1. Navigate to **[https://desktop.wxcc-us1.cisco.com/]**(https://desktop.wxcc-us1.cisco.com/) in a new browser tab
2. Enter the agent’s **Username** which you created in the previous lab.
3. Enter the **Password** for the appropriate Username
4. In the Station Login pane, select **"Extension"** and input the configured number for that user. 
**Note** Please use only Extension for this lab
6. Select the *Team_wxcclab_<**your name or company name>**, with default layout. 
7. Click **_Submit_**
			
If you are successfully logged in the Agent Desktop you have completed this section and you can continue with the next part!



# 2. Agent Desktop Overview

* The Agent Desktop is divided in 6 sections: **Task List, Horizontal Header, Interaction Control, Auxiliary Information, Agent Interaction History and Navigation bar**. In *Image 1* you can see a general view of the Agent Desktop and where each section is located.




* **Watch the following video**, where each of the sections and their main options are explained. You will get a better idea of how the Agent Desktop look like and how to use it.

[VIDEO]


* Then, try to spend little time to **play and explore the Agent Desktop**.


* Finally, in order to make sure that you have understood the basic concepts, we ask you to **complete the following tasks**:
   - **Verify that Agent can see reports**
   - **Download the Agent Dekstop User Guide**


 


# 3. Configure the User Profile

## 3.1 Change Notifications setting and volume
1. Scroll down to **_User Settings_**
2. Click on **_Notification Settings_**
3. **Toggle** any of the 3 options to **enable or disable** different notifications
4. Move the **Sound Volume** toggle bar
5. You'll test this in the next lab.
6. Check this when you receive a notification
		
## 3.2 Switch to Dark Mode
1. Go again under **_User Settings_**
2. Toggle the **_Switch to Dark Mode_** button to enable or disable it
		
## 3.3 See the list of the keyboard shortcuts
1. Scroll down to **_Help_**
2. Click on **_Keyboard Shortcuts_** or press **Ctrl+Alt+F**
3. **See the list** of the keyboard shortcuts
4. Find and test the combination to make the Agent status **_'Available'_**
		
## 3.4 Download Error Report
1. Scroll down to **_Help_**
2. Click on **_Keyboard Shortcuts_** or press **Ctrl+Shift+2**
3. Find the downloaded **error reports** file in your machine



# 4. Custom Desktop Layout

## 4.1 Download default desktop Layout
1. Login to **[https://portal.wxcc-us1.cisco.com](https://portal.wxcc-us1.cisco.com)** with admin credentials​
2. Navigate to **_Provisioning_ –> _Desktop Layout_**​
3. Click on ellipses **(…)** of Global Layout and select **_Edit_** ​
4. Click on **_Download_** button to download the **Default Desktop Layout.json** file

## 4.2 Customize default desktop layout with logo and title
1. Open the **Default Desktop Layout.json** file with any text editor (e.g. Notepad or Sublime text)​
2. Modify the **_appTitle_** key value with your company name in order to change Agent Desktop tittle
3. Modify the **_logo_** key value with your company logo URL or use this CiscoLive logo url: **https://ayankovs-ccp-s3.s3.eu-west-3.amazonaws.com/CiscoLiveLogo.jpg**
4. **_Save As_** the JSON file with a distinguishable name

## 4.3 Upload the custom desktop layout 
1. Go again to **_Desktop Layout_** module in the **[Tenant Portal](https://portal.wxcc-us1.cisco.com)**
2. Click on **_New Layout_**
3. Provide any preferable **name and description** 
4. Select *Team2_wxcclab_<**your name or company name>** as Team		
5. Click **_Upload_** button to upload the modified JSON file​		
6. Click **_Save_** button to apply the layout.

## 4.4 Associate the custom desktop layou to other team
1. Go to the **_Team_** module
2. Click on ellipses **(…)** of *Team2_wxcclab_<**your name or company name>** and select **_Edit_**
3. Modify the **_Desktop Layout_** field with the new Desktop Layout created before
4. Login in the **[Agent Desktop](https://desktop.wxcc-us1.cisco.com/)**

## 4.5 Verify the new custom desktop layout
1. Open the **_User Profile_** and click on the arrow **'>'** under **_Team_**
2. Change the team of the agent to *Team2_wxcclab_<**your name or company name>**
3. Click on **_Save Team Selection_**
4. **Confirm** the changes
5. **Wait** some seconds to see the result

## 4.6 Restore Default Desktop Layout
1. Open the **_User Profile_**
2. Scroll down to **_User Settings_**
3. Click on **_Reset Entire Desktop Layout_**
4. **Confirm** the reset layout




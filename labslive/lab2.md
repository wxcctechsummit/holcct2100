# Lab 2: New Agent Desktop Experience

Video example

<iframe width="560" height="315" src="https://www.youtube.com/embed/KZgUvCKh284" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

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

1. Navigate to **https://desktop.wxcc-us1.cisco.com/** in a new browser tab
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
   **- Verify that Agent can see reports**
   **- Download the Agent Dekstop User Guide**


 


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
3. See the list of the keyboard shortcuts
4. Find the combination to make the Agent status **_'Available'_**
		
## 3.4 Download Error Report
1. Scroll down to **_Help_**
2. Click on **_Keyboard Shortcuts_** or press **Ctrl+Shift+2**
3. Find the downloaded **error reports** file in your machine



# 4. Custom Desktop Layout

## 4.1 Download default desktop Layout
1. Login to https://portal.wxcc-us1.cisco.com/ with admin credentials​
2. Navigate to Provisioning –> Desktop Layout​
3. Click on ellipses (…) of Global Layout to edit ​
4. Now click on edit
5. Click on download button to download the Default Desktop Layout.json file

## 4.2 Customize default desktop layout with logo and title
1. Open the Default Layout JSON in any text editor (e.g. Notepad or Sublime text)​
2. Modify the appTitle key value with your company name in order to change Agent Desktop tittle
3. Modify the logo key value with your company logo URL or use this CiscoLive logo url: https://ayankovs-ccp-s3.s3.eu-west-3.amazonaws.com/CiscoLiveLogo.jpg
4. Save As” the JSON file with a distinguishable name


## 4.3 Upload the custom desktop layout 
1. Go again to Desktop Layout module in Tenant Portal
2. Click on 'New Layout'
3. Provide any preferable name and description 
4. Click on Team textbox the already configured Team2_wxcclab alternative Team		
5. Click Upload button to upload the modified JSON file​		
6. Click Save button to apply the layout.


## 4.4 Change the agent team and verify the customized desktop layout
1. Go to the Teams module, modify your team and put the new Desktop Layout
2. Again in the Agent Desktop, open the User Profile and click on the arrow '>' to change the team of the agent
3. Save Team Selection


## 4.5 Restore Default Desktop Layout
1. Click on Restore Default Layout




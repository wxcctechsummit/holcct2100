---
title: "Lab 2: New Agent Desktop Experience"
---

# Custom Desktop Layout

Video example

<iframe width="560" height="315" src="https://www.youtube.com/embed/KZgUvCKh284" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

# Table of Contents

- [1. Access to the Agent Desktop](#1-download-default-desktop-layout)
- [2. Agent Desktop Overview](#2-customize-default-desktop-layout-with-logo-and-title)
- [3. Configure the User Profile](#3-upload-the-custom-desktop-layout-an-verify)
- [4. Custom Desktop Layout](#4-assign-header-widget-and-nav-bar-widget)

# Introduction

## Lab Objective

The objective of this lab is to explore the New Agent Desktop, in order to be familiar with the its new structure, learn about recently released features and be able to configure basic options.

## Pre-requisites

For doing this lab, you need first to complete the previous Lab 1: Control Hub and Admin Portal. You labs include the following:
1. Administrator access to the Tenant Portal
2. Agent created and configured
3. Agent is part of 2 Teams
4. User is assigned to a Webex Calling extension


### 1. Access to the Agent Desktop

1. Navigate to https://desktop.wxcc-us1.cisco.com/ in a new browser tab
2. Enter the agent’s Username which you created in the previous lab.
3. Enter the Password for the appropriate Username
4. In the Station Login pane, select extension and input the configured number for that user. 
			Note: Please use only Extension for this lab
5. Select the team1, with default layout. 
6. Click Submit
			
If you are successfully logged in the Agent Desktop you have completed this section and you can continue with the next part!



### 2. Agent Desktop Overview

 * The Agent Desktop is divided in 6 sections: Task List, Horizontal Header, Interaction Control, Auxiliary Information, Agent Interaction History and Navigation bar. In Image 1 you can see a general view of the Agent Desktop and where each section is located.

* Watch the following video, where each of the sections and their main options are explained. You will get a better idea of how the Agent Desktop look like and how to use it.

[VIDEO]

* Then, try to spend little time to play and explore the Agent Desktop.

* Finally, in order to make sure that you understand the main idea we ask you to complete the following tasks:
		 - Verify that Agent can see reports
   - Display the help guide


 


### 3. Configure the User Profile

		ii. Change Notifications setting and volume
		○ Scroll down to User Settings
		○ Click on Notification Settings
		○ Toggle any of the 3 options to enable or disable different notifications
		○ Move the Sound Volume
		○ You'll test this in the next lab.
		○ Check this when you receive a notification
		
		iii. Switch to Dark Mode
		○ Go again under User Settings
		○ Toggle the Switch to Dark Mode button to enable or disable it
		
		iv. See the list of the keyboard shortcuts
		○ Scroll down to Help
		○ Click on Keyboard Shortcuts or press Ctrl+Alt+F
		○ See the list of the keyboard shortcuts
		○ Find the combination to make the Agent status 'Available'
		
		V. Download Error Report
		○ Scroll down to Help
		○ Click on Keyboard Shortcuts or press Ctrl+Shift+2
  ○ Find the error reports in your machine


### 4. Custom Desktop Layout
* Open the layout JSON file in any text editor e.g. 
* Notepad or Sublime text.(be careful copying from PowerPoint  might add unwanted spaces/characters... causing the JSON to * * fail on load) use an online [JSON formatter](https://jsonformatter.org/) to clean up if need be.​
* Modify the header section as mentioned in video
* Modify the navigation section as mentioned below​
* “Save As” the JSON file with a unique preferable nam

Changelog:

| **Version** | **Comments** | **Author(s)** | **Date** |
| --- | --- | --- | --- |
| 1.0 | Initial Release | Sameer Yadav (sameyada) | 08 Jan 2021 |

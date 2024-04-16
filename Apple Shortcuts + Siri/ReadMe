# Apple Shortcuts to Rewst

**Apple Shortcuts** is a automation tool built into the iOS, iPadOS, WatchOS, and MacOS lines of products produced by Apple Inc. 

**Rewst.io** is a Robotic Process Automation (RPA) platform that integrates tools, mostly targeted at MSPs. It allows you to build flows on visual canvasses without any coding or agents required.


The workflows, form, and docs attached allow you to implement Rewst, Apple Shortcuts, and ConnectWise PSA (formerly ConnectWise Manage). 

## Pre-Requisites

* A Rewst.io instance
* An Apple device with Shortcuts installed
* A ConnectWise PSA instance


> [!NOTE]  
> These workflows are built around using ConnectWise PSA. Via some simple tweaks, you can modify the workflow to work with other PSAs or tools that Rewst supports. This template is purely meant to serve as an example.


<br>
<br>

## Workflow Import
<br>

Attached within this repo is an Template Workflow that will create a ticket based on the information you specify in the Apple Shortcut. **It is recommended you install the workflow and setup a trigger before importing the Apple Shortcut**. 
<br>
<br>

## Where do I find the inputs for a scheduling request

If your a pro, its easily found in the output of each option gen. 

If you are relatively new to Rewst, there is a ```Generate TimeZest Scheduling Inputs``` form that will ask you who you want to schedule, what appointment to use, and how the request should be generated. The information to input will be emailed to you, along with shown in the form UI.
<br>

## Setup Webhook

After importing the template workflow, please complete these steps:

1. Create a trigger
   * Set Trigger Type to ```Core - Webhook```

2. Integration Overrides (optional)
   * If needed, add integration overrides to your CW PSA instance

3. Trigger Parameters
   * Please set the following variable, all others can remain as default or be modified as you see fit.
      * Allowed Methods: ```POST```

4. Activate Trigger To Run For
   * Enable the organization(s) you wish to allow webhook requests

5. Save your trigger

6. Copy the Webhook URL for the organization you wish to setup and note it, you will need it later.

<br>

## Setup Shortcut

After downloading :

1. Create a trigger
   * Set Trigger Type to ```Core - Webhook```

2. Integration Overrides (optional)
   * If needed, add integration overrides to your CW PSA instance

3. Trigger Parameters
   * Please set the following variable, all others can remain as default or be modified as you see fit.
      * Allowed Methods: ```POST```

4. Activate Trigger To Run For
   * Enable the organization(s) you wish to allow webhook requests

5. Save your trigger

6. Copy the Webhook URL for the organization you wish to setup and note it, you will need it later.

<br>

> [!IMPORTANT]  
> If you get a failure or unable to authorize when testing, check with the Rewst ROC. Usually, it's a misconfiguration when adding the custom API.
<br>

> [!TIP] 
> Questions, bugs, issues? There is a [thread in Rewst's discord](https://discord.com/channels/936789089703845988/1195181085450063932) regarding TimeZest. Sound off in this thread with questions to receive support from the Rewst community. 

# Apple Shortcuts to Rewst

**Apple Shortcuts** is a automation tool built into the iOS, iPadOS, WatchOS, and MacOS lines of products produced by Apple Inc. 

**Rewst.io** is a Robotic Process Automation (RPA) platform that integrates tools, mostly targeted at MSPs. It allows you to build flows on visual canvasses without any coding or agents required.


The workflows, form, and docs attached allow you to implement Rewst, Apple Shortcuts, and ConnectWise PSA (formerly ConnectWise Manage). 

## Pre-Requisites

* A Rewst.io instance
* An Apple device with Shortcuts installed
* A ConnectWise PSA instance


> [!NOTE]  
> This workflow & shortcut are built around using ConnectWise PSA. Via some simple tweaks, you can modify the workflow to work with other PSAs or tools that Rewst supports. This template is purely meant to serve as an example.


<br>
<br>

## Workflow Import
<br>

Attached within this repo is an Template Workflow that will create a ticket based on the information you specify in the Apple Shortcut. **It is recommended you install the workflow and setup a trigger before importing the Apple Shortcut**. 
<br>
<br>

1. Download the JSON bundle to your device

2. In Rewst, use the upload button to upload the bundle into your workflows
   

## Setup Webhook

After importing the template workflow, please open the workflow complete these steps:

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

## Import Shortcut

After downloading the shortcut to your Apple device, open it and follow the steps below.

> [!TIP] 
> The steps below are formatted around setup on a MacOS device, but the principles remain for iOS & iPadOS. 

1. Open the shortcut file
   * An ```Add Shortcut``` button will be shown after the Shortcut file has been verified as safe by Apple's servers

> [!IMPORTANT]  
> From this point, a form will be shown with inputs for the shortcut. A majorify of these inputs will be pulled from Rewst.io. 

2. In the ```What is your personal email``` field, add your email
   * This will be used to open a ticket with you as the contact (there is logic to open on behalf of another contact as well)

3. In Rewst, retrieve the ConnectWise PSA board IDs you wish to specify. The workflow is configured with two as default.
   * We usually reccomend using your helpdesk or equivilent as the first board, with a secondary board such as a ROC as the second.
      * Keep a note of which board ID lines up with each board, the Shortcuts UI wont display the board ID or name.
    * Fill the ```board ID``` fields accordingly

4. Fill the ```Webhook URL``` field with the webhook created earlier

5. In the ```header information``` field, add the following headers with the corresponding key and value pairs

    | Key  | Value |
    | ------------- | ------------- |
    | x-rewst-secret  | ```fill the rewst-secret org variable here``` |
    | summary  | *leave empty* |
    | description  | ```Apple Shortcut via Rewst Submission```|
    | client_email  | *leave empty* |
    | board  | *leave empty* |

6. Click ```Add Shortcut```. The shortcut should now import into Apple Shortcuts. 

> [!IMPORTANT]  
> There is still work to be done to make the shortcut operational.
<br>

## Finish Shortcut Setup

1. Open the shortcut editor
   * This can be done by right clicking on the imported shortcut and selecting ```edit```
   * You will notice the inputs provided have populated fields in the workflow editor.

2. Locate the ```Get contents of``` action
   * It should list the URL you provided for the webhook in the title

3. Click ```Show more```

4. You will notice the Headers setup earlier are now shown
    * We will be filling the fields that were omitted during import. Double click the value field to begin editing.

        | Key  | Value |
        | ------------- | ------------- |
        | Summary  | Right click and choose ```Insert Variable \ Summary``` |
        | client_email  | Right click and choose ```Insert Variable \ contactID``` |
        | board  | Right click and choose ```Insert Variable \ Board``` |

6. Close the editor (your work will auto-save)


## Run the shortcut

* In the shortcuts homepage, you can tap the shortcut to run it
* You can add the shortcut to your desktop, iOS Homescreen, Action Button (if equipped), or any other location Shortcuts are supported.
* Via Siri
    * It is reccomended you rename the shortcut. Doing so will make invoking the shortcut via Siri easier. Simply state the workflow name.
> [!NOTE]  
> Avoid using names that are similar to built-in commands within Siri. Unique names are more likely to behave as expected.

> [!TIP] 
> Questions, bugs, issues? There is a [thread in Rewst's discord](https://discord.com/channels/936789089703845988/1228435591549685862) regarding this workflow. Sound off in this thread with questions to receive support from the Rewst community. 

## Improving your shortcut

* The shortcut provided is simply a template. You can create additonal logic inside the shortcut to provide more data to Rewst.
    * Ask for a five word summary of the issue
    * Ask for a phone number for callback
    * Ask for priority
* The only limits are what you can ask via Shortcuts, and passing that data into a header cleanly.
   * Remember to make sure that both your header and the workflow in Rewst are rebuild to account for the new data you are inputting.

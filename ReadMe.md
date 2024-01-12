# TimeZest Custom API Integration - Rewst.io

**TimeZest** is a meeting scheduling tool designed specifically for MSPs. It helps eliminate scheduling conflicts and streamlines ticket resolution. 

**Rewst.io** is a Robotic Process Automation (RPA) platform that integrates tools, mostly targeted at MSPs. It allows you to build flows on visual canvasses without any coding or agents required.


The workflows, form, and docs attached allow you to implement Rewst, TimeZest, and ConnectWise PSA (formerly ConnectWise Manage). 

## Pre-Requisites

* A Rewst.io instance
* A TimeZest instance
* A ConnectWise PSA instance


> [!NOTE]  
> These workflows are built around using ConnectWise PSA. Via some simple tweaks, you can modify the API to work with other PSAs that TimeZest supports.


<br>
<br>


## Setup Custom Integration in Rewst

Integration setup well [documented here](https://docs.rewst.help/documentation/integrations/other/custom-integrations/integration-setup). When completing the "Configuration Steps", make sure to complete these tasks:

1. Authentication Method tab
   * Set hostname to ```https://api.timezest.com```
   * Set Authentication Method to: ```API Key```

2. Authentication Details
   * Create and enter the [API Key](https://app.timezest.com/settings/api_keys) from your TimeZest account in the ```API Key``` field
   *  Set the "API Key Header Name" to ```Authorization```
3. Test Configuration
   * At the final step, you can check to make sure the credentials are working by calling against an endpoint. Rewst should output a success or failure.
      * Test Endpoint: ```v1/scheduling_requests```
<br>

> [!IMPORTANT]  
> If you get a failure or unable to authorize when testing, check with the Rewst ROC. Usually, it's a misconfiguration when adding the custom API.
<br>

## Workflows
<br>

See folders for information on each workflow. **It is recommended you install all of the workflows and forms for a complete install**. 
<br>

> [!WARNING]  
> If you have multiple custom integrations, please ensure the corresponding workflows are configured to use the correct integration.


<br>

## Where do I find the inputs for a scheduling request

If your a pro, its easily found in the output of each option gen. 

If you are relatively new to Rewst, there is a ```Generate TimeZest Scheduling Inputs``` form that will ask you who you want to schedule, what appointment to use, and how the request should be generated. The information to input will be emailed to you, along with shown in the form UI.
<br>


> [!TIP] 
> Questions, bugs, issues? There is a [thread in Rewst's discord](https://discord.com/channels/936789089703845988/1195181085450063932) regarding TimeZest. Sound off in this thread with questions to receive support from the Rewst community. 

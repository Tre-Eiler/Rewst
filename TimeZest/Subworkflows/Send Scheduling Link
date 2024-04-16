# Workflow for TimeZest Scheduling Request

This workflow is designed to generate a TimeZest scheduling request via API. It requires the following inputs:

* ConnectWise PSA ticket ID
* Resource ID from TimeZest
* Appointment ID from TimeZest
* Scheduling Method (POD or generate_URL)

If you don't know the ID for the resource and appointment IDs, check out the Option-Gen workflows in this repo.


## Pre-Requisites

* A Rewst.io instance
* A TimeZest instance
* Custom Integration for TimeZest configured in Rewst


## How to use this workflow

After installing the workflow, its designed to be implemented into another flow as a "Sub-Workflow". It will ask you for the inputs noted above. From there, if you select "POD" scheduling, it will email the end user attached to the ticket for scheduling based on your TimeZest config. If you selected "generate_URL", it won't contact the user. Regardless of the method, a URL will be outputted into the CTX variables that you can then manipulate and utilize eleswhere. 

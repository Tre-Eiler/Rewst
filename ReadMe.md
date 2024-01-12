# TimeZest Custom API Integration - Rewst.io

**TimeZest** is a meeting scheduling tool designed specifically for MSPs. It helps eliminate scheduling conflicts and streamlines ticket resolution. 

**Rewst.io** is a Robotic Process Automation (RPA) platform that integrates tools, mostly targeted at MSPs. It allows you to build flows on visual canvasses without any coding or agents required.


The workflows, form, and docs attached allow you to implement Rewst, TimeZest, and ConnectWise PSA (formerly ConnectWise Manage). 

## Pre-Requisites

* A Rewst.io instance
* A TimeZest instance
* A ConnectWise PSA instance

(These workflows are built around ConnectWise PSA. Via some simple tweaks, you can modify the API to work with other PSAs that TimeZest supports.)

## Setup Custom Integration in Rewst

Integration setup well [documented here](https://docs.rewst.help/documentation/integrations/other/custom-integrations/integration-setup). When completing the "Configuration Steps", make sure to complete these tasks:

1. Authentication Method tab
   * Set hostname to ```https://api.timezest.com```
   * Set Authentication Method to: ```API Key```

2. Authentication Details
   * Create and enter the [API Key](https://app.timezest.com/settings/api_keys) from your TimeZest account in the ```API Key``` field
   *  Set the "API Key Header Name" to ```Authorization```
3. If prompted, you can test the connection by providing the following endpoint. Rewst should ouput a suceess or failure.
   * Test Endpoint: ```v1/scheduling_requests```



## Upload Workflows

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## Upload Workflows

Pull requests are welcome. For major changes, please open an issue first
to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)

---
layout: default
title:          "Debug Interface"
lead:           ""
description:    ""
keywords:       "datasdk"
permalink:       /debug_interface
lang:           "en"
---

# Debug Interface
---
Debug Interface provides a check mechanism to help App publishers understand the integration status. When Vpon Data SDK is integrated with SDK debug_mode enabled, App publishers can see the checking messages on the developer console.

Debug Interface checks SDK integration in 3-steps: ***SDK Initialization***, ***SDK Info Collection***, and ***Endpoint Connection***.

When start running App, ***SDK Initialization*** step will check SDK initialization status and display the device basic information in the developer console shown as follows.
```
[VponData] Start SDK integration tests...
[VponData] Checking SDK and device status...
[VponData] --SDK Version: iOS V2.0.0
[VponData] --License key: XXXXXXXX
[VponData] --CustomID: YYYYYYYY
[VponData] --Device Model Name: iPhone 12,3
[VponData] --Device OS: iOS 13.5.1
[VponData] --Device Limited_Ad_Tracking: False
[VponData] Succeed in initializing SDK. 
```

***SDK Info Collection*** and ***Endpoint Connection*** examine Send Event status when an App event occurs or triggers. The messages are shown as follows in the developer console:
```
[VponData] Checking triggered event data...
[VponData] --Collect Time: 2020-11-01 17:20:45 UTC+0
[VponData] --Event Type: Launch
[VponData] Checking Vpon endpoint status... 
[VponData] Succeed in sending data to Vpon endpoint. Endpoint response code : 200.
[VponData] Pass all SDK integration tests.
```
However, App publishers may see error messages if inappropriate setting occurs shown as follows:

```
[VponData] Start SDK integration tests...
[VponData] Checking SDK and device status...
[VponData] License key is invalid. 
[VponData] Fail to initialize SDK. Please check the required settings in Vpon Data SDK website. 
```
These error messages indicate that License key is invalid, which remind App publishers to check License key setting when calling SDK API.

```
[VponData] Fail to receive Vpon endpoint’s feedback. Endpoint response code : 0(-1009, The Internet connection appears to be offline.). Please make sure your network connection is stable and check Vpon’s endpoint connection again.
```
These above error messages indicate that the device is not connected to network or the network is not stable. 

If some errors keep unsolved, App publishers can collect all the messages with [VponData] header in developer console, and then send the messages to Vpon Contact: datasdk.support@vpon.com for further supports.

***Reminder: If everything goes well, App publishers have to disable debug_mode manually before submitting App to marketplaces.***

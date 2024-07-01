---
title: " Cisco Packet Tracer (CPT) Lab Solutions - Connect to a Web Server."
date: 2024-06-29 +0100
categories: ["Cisco Networking Academy", "Cisco Packet Tracer Labs"]
tag: [cisco, router, dhcp, web, server]
description: Easy way to connect your device to a web server.
---

## Overview

{: .prompt-info }

> This Cisco Packet Tracer lab is a property of the Cisco Networking Academy, [Skills for all with Cisco](https://skillsforall.com/ "Skills for all with Cisco"). This article seeks to bring solutions by displaying images and providing answers to the questions in the lab for better understanding.
> {: .prompt-info }

{: .prompt-tip }

> Click the [Cisco Packet tracer file](https://skillsforall.com/content/nb/1.0/courses/content/m8/en-US/assets/8.1.3-packet-tracer-connect-to-a-web-server.pka "Cisco Packet tracer file") to get the lab file to follow up with the solution.

### Objectives

Observe how packets are sent across the Internet using IP addresses.

## Part 1: Verify connectivity to the web server

<p style="text-align:center"><img src="images
\cws_display1.png" /></p>

a. Open the source host command prompt window. Select **PC0**.

b. Select the Desktop Tab > Command Prompt.

c. Verify connectivity to the web server. At the command prompt, ping the IP address of the web server by entering **ping 172.33.100.50**.

```
PC> ping 172.33.100.50



Pinging 172.33.100.50 with 32 bytes of data:


Reply from 172.33.100.50: bytes=32 time=0ms TTL=127

Reply from 172.33.100.50: bytes=32 time=0ms TTL=127

Reply from 172.33.100.50: bytes=32 time=0ms TTL=127

Reply from 172.33.100.50: bytes=32 time=0ms TTL=127


Ping statistics for 172.33.100.50:

Packets: Sent = 4, Received = 3, Lost = 1 (25% loss),

Approximate round trip times in milli-seconds:

Minimum = 0ms, Maximum = 0ms, Average = 0ms
```

<p style="text-align:center"><img src="images
\cws_display2.png" /></p>

A reply verifies connectivity from the client to the destination web server. The reply may time out initially while devices load and ARP is performed.

d. Close the command prompt window only, by selecting the x within the command prompt window. Be sure to leave the PC0 configuration window open.

## Part 2: Connect to the Web Server via the web client

a. In the Desktop tab on PC0, select **Web Browser**.

b. Enter **172.33.100.50** into the URL and click **Go**. The web client will connect to the web server via the IP address, and open the web page.

<p style="text-align:center"><img src="images
\cws_display3.png" /></p>

Question:
What messages did you see after the web page has finished loading?

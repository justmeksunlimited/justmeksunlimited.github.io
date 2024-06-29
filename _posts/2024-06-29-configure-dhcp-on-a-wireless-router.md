---
title: " Cisco Packet Tracer (CPT) Lab Solutions - Configure DHCP on a Wireless Router."
date: 2024-06-29 +0100
categories: ["Cisco Networking Academy", "Cisco Packet Tracer Labs"]
tag: [cisco, router, dhcp]
description: Simple steps to configure ssh in your PC
---

## Overview

{: .prompt-info }

> This Cisco Packet Tracer lab is a property of the Cisco Networking Academy, [Skills for all with Cisco](https://skillsforall.com/ "Skills for all with Cisco"). This article seeks to bring solutions by displaying images and providing answers to the questions in the lab for better understanding.
> {: .prompt-info }

{: .prompt-tip }

> Click the [Cisco Packet tracer file](https://skillsforall.com/content/nb/1.0/courses/content/m11/en-US/assets/11.2.3-packet-tracer---configure-dhcp-on-a-wireless-router.pka "Cisco Packet tracer file") to get the lab file to follow up with the solution.

### Objectives

- Connect 3 PCs to a wireless router

- Change the DHCP setting to a specific network range

- Configure the clients to obtain their address via DHCP

### Background / Scenario

A home user wants to use a wireless router to connect 3 PCs. All 3 PCs should obtain their address automatically from the wireless router.

### Instructions

### Part 1: Set up the network topology

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display1.png)

a. Add three generic PCs.

b. Connect each PC to an Ethernet port to the wireless router using straight-through cables.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display2.png)

### Part 2: Observe the default DHCP settings

a. After the amber lights have turned green, click **PC0**. Click the **Desktop** tab. Select **IP Configuration**. Select **DHCP** to receive an IP address from **DHCP Enabled Router**.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display3.png){: width="351" height="354" }

---

**Question 1**:  
Record the IP address of the default gateway:

<details>
    <summary ><strong>Click here for answer</strong></summary>

    192.168.0.1

</details>

---

b. Close the **IP Configuration** window.

c. Open a Web Browser.

d. Enter the IP address of the default gateway recorded earlier into the URL field. When prompted, enter the username **admin** and password **admin**.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display4.png){: width="351" }

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display5.png){: width="351" }

e. Scroll through the Basic Setup page to view default settings, including the default IP address of the wireless router.

f. Notice that DHCP is enabled, the starting address of the DHCP range and the range of addresses available to clients.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display6.png){: width="351" height="354" }

### Part 3: Change the default IP address of the wireless router.

a. Within the Router IP Settings section, change the IP address to: **192.168.5.1**.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display7.png){: width="351" height="354" }

b. Scroll to the bottom of the page and click **Save Settings**.

c. If it is done correctly, the web page will display an error message. Close the web browser.

d. Click **IP Configuration** to renew the assigned IP address. Click **Static**. Click **DHCP** to receive new IP address information from the wireless router.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display8.png){: width="351" height="354" }

e. Open the web browser, enter the IP address **192.168.5.1** in the URL field. When prompted, enter the username **admin** and password **admin**.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display9.png){: width="351" height="354" }

### Part 4: Change the default DHCP range of addresses.

a. Notice the DHCP Server Start IP Address is updated to the same network as the Router IP.

b. Change the Starting IP Address from 192.168.5.100 to **192.168.5.126**.

c. Change the Maximum Number of Users to **75**.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display10.png){: width="351" height="354" }

d. Scroll to the bottom of the page and click **Save Settings**. Close the web browser.

e. Click **IP Configuration** to renew the assigned IP address. Click **Static**. Click **DHCP** to receive new IP address information from the wireless router.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display11.png){: width="351" height="354" }

f. Select **Command Prompt**. Enter **ipconfig**.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display12.png){: width="351" height="354" }

---

**Question 2**:  
Record the IP address for PC0:

<details>
    <summary ><strong>Click here for answer</strong></summary>

    192.168.5.126

</details>

---

### Part 5: Enable DHCP on the other PCs.

a. Click **PC1**.

b. Select **Desktop** tab.

c. Select IP Configuration.

d. Click **DHCP**.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display13.png){: width="351" height="354" }

---

**Question 3**:  
Record the IP address for PC1:

<details>
    <summary ><strong>Click here for answer</strong></summary>

    192.168.5.127

</details>

---

e. Close the configuration window.

f. Enable DHCP on **PC2** following the steps for PC1.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display14.png){: width="351" height="354" }

### Part 6: Verify connectivity

a. Click **PC2** and select the **Desktop** tab.

b. Select Command Prompt.

c. Enter **ipconfig** at the prompt to view the IP configuration.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display15.png){: width="351" height="354" }

d. At the prompt, enter **ping 192.168.5.1** to ping the wireless router.

e. Enter **ping 192.168.5.126** to ping PC0 at the prompt.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display16.png){: width="351" height="354" }

f. At the prompt, enter **ping 192.168.5.127** to ping PC1.

![alt text](../assets/img/configure-dhcp-on-a-wireless-router/dhcp_display17.png){: width="351" height="354" }

g. The pings to all devices should be successful.

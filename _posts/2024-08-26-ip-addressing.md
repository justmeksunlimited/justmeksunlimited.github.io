---
title: "Internet Protocol Addressing"
date: 2024-06-27
categories: [Networking]
tag: [dhcp]
description:
---

Internet Protocol (IP) addresses can be statically by static addressing system especially for IPv4 addresses, or dynamically by dynamic addressing system for IPv4 and IPv6 addresses.

### Static Addressing System

Static addressing is a procedure where the network administrator manually enters or configure IP address information on hosts.

### Static IPv4 Address Assignment

IPv4 addresses can be assigned either statically or dynamically. In a static assignment, the minimum network information the network administrator must manually configure includes

- **IP Address**: This identifies the host on the network

- **Subnet Mask**: This is used to identify the network on which the host is connected.

- **Default Gateway**: This identifies the networking device that the host uses to access the internet or another remote network.

### Benefits of Static Addressing

Static address for instance are useful for printers, servers, and other networking devices that need to be accessible to clients on the network. Hosts that normally access a server at a particular IPv4 address, would be unable to if the address of the server changed, hence, static addressing is used to maintain the addresses of specific network devices.

Static assignment of addressing information provides increased control of network resources, but it can be time consuming to enter the information on each host. However, host only perform basic error checks on IPv4 address when the IPv4 addresses are entered statically. Therefore, errors are likely to occur.

It is important to maintain an accurate and clear list of which IPv4 addresses are assigned to specific devices when using static IPv4 addressing. These addresses are permanently assigned addresses on network devices except they are manually changed and also, they are not normally reused on other network devices when assigned to particular devices.

### Dynamic Addressing System

On large networks, or when the user population changes frequently, new users may arrive with may be laptops, and need connections. Others may have new computer or workstations that need to be connected. Rather than use static addressing for each connection, it is easier and more efficient to have IP addresses assigned automatically. This is done using a protocol known as **Dynamic Host Configuration Protocol (DHCP)**.

When a host connects to the network, the DHCP server is contacted and an address is requested. The DHCP server chooses an address from a configured range of address called a pool and assigns(leases) it to the host.

DHCP can allocate IP addresses for a configurable period of time, called a lease period. The lease period is an important DHCP setting. When the lease period expires or the DHCP server gets a DHCP RELEASE message, the address is returned to the DHCP pool for resuse. Users can freely move from location to location and easily re-establish network connections through DHCP.

### Benefits of Dynamic Addressing with DHCP

DHCP is generally the preferred method of assigning IPv4 addresses to hosts on large networks because it reduces the burden on network support staff and virtually eliminates entry errors.

Another benefit of DHCP is that an address is not permanently assigned to a host but it is only leased for a period of time. If the host is powered down or taken off the network, the address is returned to the pool for reuse. This is especially helpful with mobile users that come and go on a network.

### Dynamic IPv4 Address Assignment

DHCP automatically assigns addressing information such as IPv4 address, subnet mask, default gateway and other configuration information. It is generally the preferred method of assigning IPv4 addresses to hosts on large networks.

DHCP for IPv4 can also be referred to as DHCPv4.
DHCP for IPv6 (DHCPv6) provides similar services for IPv6 clients.

One major difference is that DHCPv6 does not provide a default gateway address. This can only be obtained dynamically from the **Router Advertisement** message of the router.

### DHCPv4 Configuration

The DHCP server is configured with a range or pool, of IPv4 addresses that can be assigned to DHCP clients. A client that needs and IPv4 address will send a DHCP Discover message which is a broadcast with a destination IPv4 address of 255.255.255.255 (32 ones) and a destination MAC address of FF-FF-FF-FF-FF-FF (48 ones). All hosts on the network will receive this broadcast DHCP frame, but only a DHCP server will reply. The server will respond with a DHCP Offer, suggesting an IPv4 address for the client. The host then sends a DHCP Request asking to use the suggested IPv4 address. The server responds with a DHCP Acknowledgment.

For most home and small business networks, a wireless router provides DHCP services to the local network clients. To configure a home wireless router, access its graphical web interface by opening the browser and entering the router default IPv4 address. The IPv4 address of 192.168.0.1 and subnet mask of 255.255.255.0 are the defaults for the internal router interface. This is the default gateway for all hosts on the local network and also the internal DHCP server IPv4 address. Most home wireless routers have DHCP Server configured by default.

### DHCPv4 Messages

When an IPv4, DHCP-configured device boots up or connects to the network, the client broadcasts a DHCP discover **(DHCPDISCOVER)** message to identify any available DHCP servers on the network. A DHCP server replies with a DHCP offer **(DHCPOFFER)** message which offers a lease to the client. The offer message contains the IPv4 address and subnet mask to be assigned, the IPv4 address of the DNS server, and the IPv4 address of the default gateway. The lease offer also includes the duration of the lease.

The client may receive multiple DHCPOFFER message if there is more than on DHCP server on the local network. Therefore, it must choose between themm, and sends a DHCP request **(DHCPREQUEST)** message that idnetifies the explicit server and lease offer that the client is accepting. A client may also choose to request an address that it had previously been allocated by the server.

Assuming that the IPv4 address request by the client, or offered by the server, is still available, the server returns a DHCP acknowledgement **(DHCPACK)** message that acknowledges to the client that the lease has been finalized. If the offer is no longer valid, then the selected server responds with a DHCP negative acknowledgement **(DHCPNAK)** message. If a DHCPNAK message is returned, then the selection process must begin again with a new DHCPDISCOVER message being transmitted. After the client has the lease, it must be renewed prior to the lease expiration through another DHCPREQUEST message.

The DHCP server ensures that all IP addresses are unique (the same IP address can not be assigned to two different network devices simultaneously). Most ISPs use DHCP to allocate addresses to their customers.

DHCPv6 has a set of messages that is similar to those for DHCPv4. The DHCPv6 messages are **SOLICIT, ADVERTISE, INFORMATION REQUEST, and REPLY**.

### DHCP Servers.

If you enter a public place say an airport or a restaurant, with wireless hotspot, DHCP makes it possible for you to access the internet. As you enter the area, your laptop DHCP client contacts the local DHCP server via a wireless connection. The DHCP server assigns an IPv4 address to your laptop.

Various types of devices can be DHCP servers as long as they are running DHCP service software. With most medium to large networks, the DHCP server is usually a local dedicated PC-based server.

With home networks, the DHCP server may be located at the ISP and a host on the home network receives its IPv4 configuration directly from the ISP. Many home networks and small businesses use a wireless router and modem. In this case, the wireless router is both a DHCP client and a server. The wireless router acts as a client to receive its IPv4 configuration from the ISP and then acts as a DHCP server for internal hosts on the local network. The router receives the public IPv4 address form the ISP, and in its role as a DHCP server, it distributes private addresses to internal hosts.

In addition to PC-based servers and wireless routers, other types of networking devices such as dedicated routers can provide DHCP services to clients, although this is not as common.

In conclusion, many networks use both DHCP and static addressing. DHCP is used for general purpose hosts, such as end user devices. While static addressing should be used for network devices such as gateway routers, switches, servers, and printers.

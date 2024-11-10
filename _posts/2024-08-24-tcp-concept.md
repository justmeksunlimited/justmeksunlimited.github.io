---
title: "TCP Concept"
date: 2024-06-27
categories: [Networking]
tag: [tcp]
description:
---

TCP, Transmission Control Protocol, which is one of the two protocols of the transport layer of the hierarchical network design, is considered a reliable, full-featured transport layer protocol, which ensures that all of the data arrives at the destination.

TCP includes fields which ensure the delivery of the application data. Thes fields require additional processing by the sending and receiving hosts.

TCP divides data into segments and it transports is similar to sending packages that are tracked from source to destination, just like a shipping order which is broken up into several packages, so that a customer can check online to see the order of the delivery.

NOTE:  
a. TCP is known to provide reliability and flow control using these basic operations.

- Number and track data segments that were transmitted to a specific host from a specific application
- Acknowledges received data
- Retransmits any unacknowledged data after a certain amount of time.
- Sequences data so as to sort out data that might arrive in wrong order.
- Sends data at an efficient rate that is acceptable by the receiver.

b. In order to maintain the state of a conversation and track the information, TCP must first establish a connection between the sender and the receiver. Thus, the reason TCP is known as a connection-oriented protocol.

c. Some applications require that all data arrives and be processed in its proper sequences. For thees applications, TCP is used as the transport protocol. For example, applications such as databases, web browsers, and email clients, require that all data that is sent arrives at the destination in its original condition. Any missing data could corrupt a communication making it either incomplete or unreadable. For example, it is important when accessing banking information over the web to make sure all the information is sent and received correctly.  
Applications that stream stored audio and video typically use TCP. The application uses TCP to perform buffering , bandwidth probing, and congestion control in order to better control the user experience.  
For example, if your network suddenly cannot support the bandwidth needed to watch an on-demand movie, the application pauses the playback. During the pause, you might see "buffering..." message while TCP works to re-establish the stream. When all the segments are in order and a minimum level of bandwidth is restored, your TCP session resumes, and the movie resumes playing.

### TCP Features

TCP supports the basic functions of data segmentation and reassembly and also provides the following services;

#### Establishes a Session:

TCP is a connection-oriented protocol that negotiates and establishes a permanent connection( or session) between source and destination devices prior to forwarding any traffic. Through this session establishment, the devices negotiate the amount of traffic that can be forwarded at a given time and the communication data between the two can be closely managed.

#### Ensures Reliable Delivery:

For many reasons, it is possible for a segment to become corrupted or lost completely, as it is transmitted over the network. TCP ensures that each segment that is sent by the source arrives at the destination.

#### Provides Same-Order Delivery:

TCP ensures segment are reassembled into the proper order by numbering and sequencing the segment. This is so, because networks may provide multiple routes that can have different transmission rates, thereby data can arrive in the wrong order.

#### Supports Flow Control

Network hosts have limited resources, that is memory and processing power. When TCP is aware that thes resource are overtaxed, it can request that the sending application reduce the rate of data flow. This is done by TCP regulating the amount of data the source transmits. Flow control can prevent the need for retransmission of the data when the resources of the receiving host are overwhelmed.

For more information on TCP, search on the RFC 793.

### TCP Header

TCP is a stateful protocol, which means it keeps track of the state of the communication session. To track the state of a session, TCP records which information it has sent and which information has been acknowledged.

Note:  
The stateful session begins with the session establishment and ends with the session termination.  
A TCP segment adds 20 bytes (160 bits) of overhead when encapsulating the application layer data.

TCP Header Fields
There are ten fields in a TCP header

1. Source Port  
   A 16-bit field used to identify the source application by port number

2. Destination Port  
   A 16-bit field used to identify the destination application by port number

3. Sequence Number  
   A 32-bit field used for data reassembly purposes.

4. Acknowledgement Number  
   A 32-bit field used to indicate that data has been received and the next byte expected from the source.

5. Header Length  
   A 4-bit field known as "data offset" that indicates the length of the TCP segment header.

6. Reserved  
   A 6-bit field that is reserved for future use

7. Control bits  
   A 6-bit field that includes bit codes or flags, which indicate the purpose and function of th TCP segment.

8. Window Size  
   A 16-bit field used to indicate the number of bytes that can be accepted at one time.

9. Checksum  
   A 16-bit field used for error checking of the segment header and data

10. Urgent  
    A 16-bit field used to indicate if the contained data is urgent.

#### Applications that use TCP

TCP is a good example of how the different layers of the TCP/IP protocol suite have specific roles.
TCP handles all tasks associated with dividing the data stream into segments, providing reliablity, controlling data flow, and reordering segments.  
TCP frees the application from having to manage any of the these tasks. Applications can simply send the data stream to the transport layer and use the services of TCP.

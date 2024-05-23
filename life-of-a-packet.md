
# Title: The Journey of a Packet: Navigating the Internet's  Core Layers

The internet functions through the seamless transmission of packets, the basic units of data exchange. This article delves into the journey of a packet across the internet's four-layer model, elucidating its critical role in networking. 

## Prerequisite:
1. Basic understanding of [Computer networks](https://www.ibm.com/topics/networking)
2. Familiarity with the [OSI model](https://aws.amazon.com/what-is/osi-model/)
3. Basic knowledge of [TCP/IP protocol suite](https://www.geeksforgeeks.org/tcp-ip-in-computer-networking/)
4. Basic networking tools e.g [WireShark](https://www.wireshark.org/docs/wsug_html_chunked/)

## The 4-Layer Internet Model
Before we begin our journey through the life of a packet, it is important that we first understand, briefly what Computer Networking is, its relevance in IT operations, Cloud services and the internet at large. 

### Computer Networking in Today's Digital Lanscape 
Computer Networking is the process of transferring and exchanging data between interconnected computing devices or nodes over a physical or wireless technology service, applying a set of rules defined as communication protocols.

Computer networking enables devices and endpoints to connect on a local area network (LAN) or larger networks like the internet or private wide area networks (WANs). This connectivity is essential for service providers, businesses, and consumers worldwide to shre resources, acess services, and communicate. Netowkring supports a wide range of activities, from telephone calls and text messaging to streaming video and teh [Internet of Things.](https://learn.microsoft.com/en-us/azure/iot/iot-introduction) 

In cloud services and internet functionality, coomputer networking is crucial. It enables seamless integration and communication between on-premises infrastrutute and cloud platforms, facilitating data transfer, application deployment, and access to cloud-based resources. Netwoking provides the underlying infrastructure for cloud services such as [virtual private clouds - VPCs,](https://learn.microsoft.com/en-us/azure/virtual-network/virtual-networks-overview) load balancers, and content delivery networks (CDNs), ensuring reliable and scalable cloud soutions. Moreover, networking is fundamental to the internet, enbling global connectivity, data exchange, and access to online services. It routes data packet across interconnected devices, ensuring the internet's reliability, perfomance and accessibility. Compputer networking is vital for both vloud services and the internet, forming the core architecture of modern infrastructure and communication.

### The Significance of Networking to End-Users
End-users should care about networking because it is essential for accessing shared resources, internet connectivity, and optimal application performance. Networking directly impacts productivity and efficiency by enabling seamless communication and collaboration. It also plays a crucial role in ensuring the security and privacy of data, protecting against unauthorized access and cyber threats. Moreover, staying informed about networking helps end-users leverage emerging technologies like cloud computing and IoT, enhancing their digital experience and personal or professional growth. Understanding the importance of networking empowers users to make informed decisions and maximize the benefits of technology in their daily lives.

### Benefits of the 4-Layer Internet Model

1. **Universal Adoption:** The TCP/IP model serves as the cornerstone of internet communication, enjoying universal adoption worldwide. It fosters seamless communication among devices from various vendors and platforms, thereby facilitating global interconnectivity in the digital realm.

2. **Scalability and Flexibility:** With its modular design, the TCP/IP model boasts scalability and flexibility, allowing for the effortless integration of new technologies and protocols. This adaptability ensures that the model can meet evolving networking demands and accommodate future advancements with ease.

3. **Interoperability:** Ensuring interoperability between diverse systems and networks, the TCP/IP model enables smooth communication across a wide array of devices and platforms. It facilitates the exchange of data between different protocols and technologies, promoting seamless connectivity in the digital landscape.

4. **Internet Standardization:** Serving as the standard for internet communication, the TCP/IP model plays a pivotal role in guiding the development and implementation of networking protocols and technologies. By providing a common framework, it promotes compatibility and uniformity across networks, thereby enhancing overall efficiency and reliability.


## Understanding The 4-Layer Internet Model
The TCP/IP model also referred to as the 4-Layer Internet Model, is a conceptual structure that outlines the protocols and standards governing data transmission across networks. It consists of four interlinked layers, each responsible for facilitating network communication. Named after its priamry protocols, TCP guarantees dependable data delivery, while IP manages data packet routing and addressing. 


|     Internet Model               |     Description               |
|--------------------|--------------------|
|  Application                  |   Bidirectional reliable byte stream between two applications, using application specific semantics (e.g HTTP, BitTorrent)                 |
| Transport                   | Guarantees correct, in-order end-to-end delivery of data                   |
| Network                   |Delivers datagram end-to-end. Best effort delivery - with no guarantees. Must use the Internet Protocol (IP)                    |
|Link                    |Delivers data over a single link between an end host and router, or between routers                    |


At the top of the 4-layer model is the Application layer, with aapplications such as BitTorrent, WorldWideWeb, etc, which communicate to its peer layer at the destination. When the application has data to transmit, it sends it to the transport layer, which has the job of delivering the data reliably or otherwise to the destination. The transport layer then forwards this data to the network layer responsible for segmenting the data into packets, each tagged with the correct destination and address. Subsequently, the packets are handed to the link layer, which ensures their delivery from one node to the next along their path. The data progresses hop by hop through routers until it reaches the destination, where it ascends through layers until it reaches the applicaiton.

All four layers facilitate reliable communication between applications in the end hosts. Each layer has a different responsibility, with higher layers building upon those beneath them, culminating in a bidirectional, reliable byte stream communication between applications.


### The Link Layer
The Link layer, or Network Access Layer, serves as the foundation of the TCP/IP protocol model functionig as the interface between the network hardware and the rest of the network satack. Its primary role is to faciliatte the transmission and reception of data across the physical network, providing a means for devices to communicate within the local area entwork (LAN). This layer defines protocols governing how data is transmitted over the network, connecting various end devices to the LAN infranstructure.

<image should be here>

Key responsibilities of the Link layer include managing communication with thhe computer's network adapter, coordinating data transmission according to the appropriate access method (e.g Ethernet, token ring), formatting data into frames for transmission, handling errors in incoming frames, and acknowledging receipt of data frames while ensuring reliable delivery through resending if necessary. Additionally, the layer assigns addresses to network interface devices enabling communicaiton with devices on other networks.

Various physcial network technologies are employed within the Network Access Layer to faciliate communication within LAN environments. These technologies include Ethernet, Token Ring, FDDI (Fiber Distributed Data Interface) for high speed networks, PPP (Point-to-Point Protocol) utilized through modems, and wireless networks such as WiFi and mobile networks. Each technology offers distinct advantages and is chosen based on factors like network speed, scalability, and deployment requirmeents. 



### The Network Layer

The network layer’s primary function is to ensure the end-to-end delivery of packets across the internet. Starting from the source and reaching the destination. Packets serve as a fundamental component in the network. Which denotes a set of data accompanied by a header that specifies its content, destination, and origin.

<image here>

Network layer packets are called datagrams. They include the data and a header containing the “to and from” addresses. The network hands the datagram to the Link layer, telling it to send it to the first link. The Link layer provides a service to the Network layer. The Link layer is saying if you give me a datagram to send, I will transmit it over one link for you.

<image here>

At the other end of the link is a “Router.” The Link layer of the router accepts the datagram from the link and hands it up to the Network layer inside the router. The Network layer on the router examines the destination address of the datagram. It then routes the datagram, one hop at a time, to its eventual destination. And it does this by sending it to the Link layer again. To carry it over to the next link, which is passed to the Network layer on the next router and so on, until it reaches the network layer of its destination.

<image should be here>

Notice that the Network layer does not need to concern itself with how the Link layer sends the datagram over each link. In fact, different Link layers work in unique ways. The “Ethernet and Wi-Fi are clearly very different.” This separation of concerns between the Network and Link layers allows each to focus on its job without worrying about how the other layer works. It also means that a single Network layer has a common way of talking to many Link layers by simply handling the datagrams to send. The modularity of each layer makes this separation of concerns possible, coupled with a well-defined API to the layer below.

On the internet, the Network layer is “special”. When we send packets to the internet, we must use the internet protocol (IP). It is the IP that holds the internet together. The IP strives to deliver datagrams to their intended dedstiantions, but it does not guarantee successful delivery. Datagrams can be lost, delivered out of sequence, or not delivered at all due to network conditions or congestions. Despite these potential issues, the internet can still function effectively. To ensure reliable and ordered delviery of data , applications require another protocol layered on top of the IP. This protocol opereates at the "[Transport Layer](#the-transport-layer)" and its responsibility is managing end-to-end communication between applications. By using rhe services provided by the Transport Layer, applications can acheive the assurance that their data will be delivered in order and without complications, even if there are network failures at the IP level. 


### The Transport Layer
The “Transmission Control Protocol” — TCP — is the most common Transport layer. The TCP’s job is to guarantee that the data sent by an application at one end of the Internet is delivered correctly to the application at the other end. If the Network layer drops some datagrams, the TCP will transmit them multiple times if needed. If the Network layer delivers them out of order — perhaps if two packets follow a different path to their destination. TCP will put the data back into the correct order again.

TCP, or Transmission Control Protocol, provides applications with a service that ensures data is delivered correctly and in the intended order, despite the unreliable nature of the underlying Network layer's datagram delivery service. This means that TCP guarantees the correct sequencing and delivery of data packets, addressing issues like packet loss, out-of-order delivery, and duplication. Applications like web and email clients greatly benefit from TCP's reliability, as it allows them to focus on their core functionalities without the need for complex internal error-handling mechanisms. By relying on TCP, these applications can delegate the responsibility of reliable data transfer, thus abstracting away the complexities of netowkr communication and ensuring a seamless and dependable data transmission.

<image should be here>

However, not every application requires a dependable or reliable delivery of data packets. Consider a scenario where video snippets are transmitted in packets during a Zoom call. If there is a network latency, multiple retransmissions of packets may not be essential. Opting to to forego retransmission ccould be the optimal choice. For applications that do not require a reliable delivery, a simpler alternative like [UDP: User Datagram Protocol](https://www.freecodecamp.org/news/tcp-vs-udp/) can be utilized instead.


### The Application Layer
The Application layer, is positioned at the top of the four-layer TCP/IP model, and it defines TCP/IP application protocols and facilitates the interface between host programs and Transport layer services for network usage.  The Application layer includes a variety of high-level such as DNS (Domain Naming System), HTTP (Hypertext Transfer Protocol), Telnet, SSH, FTP (File Transfer Protocol), TFTP (Trivial File Transfer Protocol), SNMP (Simple Network Management Protocol), SMTP (Simple Mail Transfer Protocol) , DHCP (Dynamic Host Configuration Protocol), X Windows, RDP (Remote Desktop Protocol) etc.

Every application interacts with the Transport layer through a well-defined API, originating from the Application layer, to access the underlying TCP or UDP service. Applictions mostly want a [bidirectional reliable byte stream](https://book.systemsapproach.org/e2e/tcp.html) between endpoints, using their own protocols to define the syntax and semantics of data exchange.

For examples, when a web client sends a GET request to a web server, it transmits the request as an ASCII string along with the URL. From the Application layer's viewpoint, the request is directed stright to its peer at the receiving end (thhe web server application), without needing to worry about the underlying transmission configuratins. The Application layer delegates the GET request to the TCP layer for accurate delivery, which in turn utilizes the services of the Netork layer, relying on the Link layer for transmission.

<image here>


## Functions of the 4-layer Internet Model
1. IP Introduces Logical Addressing:
TCP/IP implements logical addressing to accommodate numerous hosts across diverse networks. IP manages this mechanism, ensuring data packets reach the appropriate networks and nodes. Techniques like network classes, subnets, and CIDR are employed to efficiently manage network addressing.

2. IP Manages Routing:
Handling the critical task of routing data packets, IP determines the next node along the transmission path from source to destination. This ensures that data packets reach their intended destinations, even if the sender is unaware of the specific location.

3. TCP Ensures Error and Flow Control:
Establishing a virtual connection between senders and receivers, TCP maintains continuous communication and incorporates error and flow control mechanisms. This enables reliable data transfer and ensures connection stability throughout the transmission process.

4. TCP Supports Applications:
TCP provides support to applications through the concept of ports, assigning unique TCP and UDP ports. This allows for the seamless differentiation of specific applications and their communication links, simplifying the communication process and enhancing application functionality.

5. DNS Provides Name Resolution:
TCP/IP relies on the Domain Name System (DNS) for name resolution services. DNS translates Fully Qualified Domain Names (FQDNs) into IP addresses, enabling users to access desired hosts on the internet using specified names.

## Understanding Packets. 
A packet consists of both the data intended for delivery and a header containing information about its destination and origin within the network. When a user requests to load an image, the image file is not transmitted from the web server to the user's computer as a single entity. Instead, it is fragmented into packets of data, transmitted across the Internet via wires, cables, etc, and subsequently reassembled by the user's computer to reconstruct the original image.

Packets are utilized in internet communication for their efficiency, reliability, scalability, and flexibility. Breaking data into smaller packets or sizes optimizes network resources, while error detection and correction mechanisms enhance reliability. The internet employs [packet switching](https://en.wikipedia.org/wiki/Packet_switching), a method where data is divided into smaller packets for efficient transmission between computers. This approach enhances network performance by allowing multiple connections to occur simultaneously over the same wires and enabling networking equipment to process packets independently. Packet switching also enhances network resilience and efficiency by permitting packets to take various paths to their destination, facilitating data exchange among billions of devices.


### What is in a packet header?

Examining the IPv4 packet header, we can see what travels with a packet to its destination. 

<IPv4 packet header image should be here>

- Bit 0: Typically refers to the first bit in a bit sequence. In the context of networking, the order in which bits are sent can depend on the network protocol being used. For instance, Ethernet and IP do not specifically define the order in which individual bits are sent on the wire, but rather the order of bytes and fields.
- IPv4 Header: Contains several critical fields used for routing and handling packets. The most important fields include:
  - Destination IP Address: Indicates the packet's intended recipient.
  - Source IP Address: Indicates the packet's origin.
  - Protocol ID: Specifies the higher-level protocol used in the data field (e.g., TCP, UDP). This field helps the destination host demultiplex arriving data, routing it to the appropriate protocol handler. For example, a Protocol ID value of 6 indicates the data contains a TCP segment, so it should be passed to the TCP processing module.

> The Internet Assigned Numbers Authority (IANA) defines over 140 different protocol numbers representing various transport and network layer protocols.

- Version: This 4-bit field specifies the IP version being used. The values are 4 for IPv4 and 6 for IPv6. The header described here is for IPv4.

- Total Length: This 16-bit field specifies the entire packet size, including the header and data, in bytes. The maximum size is 65,535 bytes (64 KB).

- Time to Live (TTL): This 8-bit field prevents packets from circulating indefinitely. Each router that forwards the packet decrements the TTL by 1. If TTL reaches zero, the packet is discarded. This mechanism ensures packets do not loop forever.

- Flags, Fragment Offset, and Identification: 
  - Identification: This 16-bit field is used to uniquely identify fragments of an original IP packet.
  - Flags: This 3-bit field controls and identifies fragments. The most significant bit is reserved. The remaining two bits are:
    - DF (Don't Fragment): If set, the packet cannot be fragmented.
    - MF (More Fragments): If set, it indicates there are more fragments. If not set, it indicates the last fragment.
  - Fragment Offset: This 13-bit field specifies the position of the fragment in the original packet, measured in 8-byte blocks.

- Type of Service (ToS) / Differentiated Services Code Point (DSCP): This field indicates the quality of service desired for the packet. It can be used by routers to prioritize packets.

- Header Length: This 4-bit field indicates the length of the IP header in 32-bit words. The minimum value is 5 (20 bytes), and the maximum value is 15 (60 bytes), accommodating optional fields.

- Header Checksum: This 16-bit field is used for error-checking the header's integrity. It ensures the header has not been corrupted in transit. If the checksum does not match the calculated value, the packet is discarded.


### Common Types of Network Packets

| Packet Type          | Purpose                                                                   | Example                               | Function                                                                                   |
|----------------------|---------------------------------------------------------------------------|---------------------------------------|-------------------------------------------------------------------------------------------|
| Data Packets         | Transport user data or application-specific information                  | Segments of emails or file downloads | Encapsulate user data and ensure delivery from source to destination                     |
| Control Packets      | Manage and control network communications                                 | TCP control packets like SYN, SYN-ACK, and ACK | Facilitate establishment, maintenance, and termination of network sessions           |
| Routing Packets      | Inform routers about network topology changes and determine best path     | OSPF and BGP packets                  | Maintain and update routing tables to ensure data takes most efficient path             |
| Fragmentation Packets | Divide large data packets into smaller fragments to accommodate MTU       | IP fragmentation packets              | Allow large packets to be transmitted over networks with smaller MTU sizes               |
| Acknowledgement Packets | Confirm successful receipt of data packets                             | TCP ACK packets                      | Provide feedback to sender that data has been received correctly, ensuring reliable transmission |
| Broadcast Packets    | Simultaneously send data to all nodes in a local network segment         | ARP requests                          | Enable network-wide communication for tasks like address resolution and network discovery |


## The Journey of a Packet
The 4-Layer Internet Model picks up a stream of data from the application layer, the transport layer breaks the stream into a segment of data that it reliably delivers to an application running on another computer. The transport layer sends this segments as network layer packets - which the network layer delivers to other computers. 

Hence, this goes from: Application [streams of data] -> transport [breaks stream of data into segments] -> network [sends network layer packets to other computers].

**The TCP Byte Stream or Bidirectional Reliable Byte Stream**

![TCP Byte Stream](1_bZhDAk2tgtCSruD_1AcUIQ.webp)

> - TCP Byte Stream: TCP provides a reliable, ordered, and error-checked delivery of a stream of bytes between applications running on hosts communicating via an IP network. It abstracts the data into a continuous stream of bytes.
> - Bidirectional: Communication occurs in both directions. Both the client and server can send and receive data simultaneously.
> - Reliable: TCP ensures that data is delivered accurately and in the same order it was sent. This is achieved through error-checking mechanisms and acknowledgment of received packets.

Almost all web traffic is over TCP. Its typical operation is between a client and a server. The server listens for a connection request. To open a connection, a client issues a connection request, which the server responds to. This exchange takes 3 messages, called the “3-way handshake.”

- The first step of the message is when the client sends a Synchronize message to the server often called the “SYN.”

- The second step is when the server responds with a synchronized message. This acknowledges the client synchronize or a “Synchronize / Acknowledge” message. This is often called a “SYN/ACK.”

- The third and final step is when the client responds by acknowledging the server synchronize often called an “ACK.”

![Transmission Protocol Stream](1_bZhDAk2tgtCSruD_1AcUIQ.webp)

From the perspective of the Network layer, packets sent to different applications on the same computer look the same. This means that to open a TCP stream to another program, we need two addresses.

- The first is the IP address: the address the Network layer uses to deliver packets to the computer
- The second is a TCP port: this tells the computer software, which application to deliver data to.

Web servers, usually run on TCP Port 80. So when we open a connection to a web server, we send IP packets to the computer’s IP address. Those IP packets have TCP segments, whose destination port is 80.

**How does an IP Packet get to its destination?**

Given that a direct physical link between a client (say, A) and a server may not exist, client A is usually connected to an intermediary, typically a router. This router, in turn, establishes connections with other routers in the network. The journey of IP packets from client A to the server involves multiple stages, referred to as “hops,” where each hop represents a connection between two routers. If client A accesses the network via a Wi-Fi connection, the hop involves wireless communication to reach the network access point. Conversely, if client A employs a wired connection like Ethernet, the data transmission traverses physical cables, eliminating the need for wireless “hops” in the client-network infrastructure connection.

The access point has a wired connection to the broader internet, so it forwards packets ( client A's packet ) along this wired hop. A router can have many links connecting to it. Upon the arrival of each packet, the router determines the appropriate outbound link for transmission. Routers possess IP addresses, which may lead to a scenario where a packet is not forwarded but instead delivered to its corresponding software.

**Inside the stream**

![Inside the stream](1_EuGF3xjKX0PNUR7LWtqIZA.webp)

**Inside each hop**

![inside each hop](1_-VaFCeLaX9Sv_TJLI_zNbQ.webp)

For example, when you log in to a router using TCP, the IP packets are destined to the router’s own IP address.

**How does a router make this decision?**

This is achieved through the use of a forwarding table, which comprises IP address patterns and their associated outbound links. When a packet arrives, it assesses which entry in the forwarding table best matches its pattern and subsequently directs the packet through the link specified in that entry. Typically, the term “best” signifies the most specific match.

The “Default” route is the least specific. It matches every IP address. If a packet arrives and there is not a specific router than the default route, the router will use the Default route.

![forwarding table](31_Iuw6hMKzGjuAJ2LLKM4yMw.webp)

## Sumary

In computer networking, a packet’s journey follows the 4-Layer Internet Model. It begins at the Application layer when an app wants to send data. The Transport layer, with protocols like TCP and UDP, deals with splitting data, controlling the flow, and finding errors. Then, at the Network layer, the packet gets wrapped in an IP header that guides it across the internet. Lastly, the Link layer ensures that the packet goes over the physical network.

When the packet reaches its destination, it reverses the steps. It begins at the Link layer, where it’s received and decoded. The Network layer looks at the IP header to find out where the packet should go. The Transport layer checks the data for problems and puts it in order if needed. Finally, the Application layer hands the data to the receiving app.

All along the way, packets are carefully handled to make sure they go from the source to the destination, and this is how data travels in computer networking.

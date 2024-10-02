# How the Internet works?

This is the crucial stage for any web security engineers to understand the basics and underlying concepts of web technologies and its' protocols. We must have knowledge about how computers exchange data over the web.

PREDECESSOR OF THE INTERNET ===> ARPANET (Advanced Research Projects Agency Network).

## TCP(Transmission Control Protocol).

The first message sent over the "ARPANET" was a LOGIN command destined for a remote computer at Stanford University. The network sent the first two letters, <code>LO</code> and then crashed. This was a problem for US military, which was looking for a way to connect remote computers so that they could continue to exchange information at any situation.

To address this problem, the network engineers developed the "Transmission Control Protocol(TCP)" to ensure a reliable exchange of information between computers.

## How data travels on the Internet?

When a computer sends a message to another machine via TCP, the message is split into data packets that are send towards their eventual destination with a destination address. If the recipient fails to acknowledge receipt of a packet, the sender resends that packet, possibly along a different network path. In this way, TCP allows computers to deliver data across a network that is expected to be unreliable.

TCP has undergone significant improvements as the internet has grown. Packets are now send with a "checksum" that allows recipients to detect data corruption and determine whether packetes need to be resent.

Sender also preemptively adjust the rate at which they send data according to how fast it's being consumed. Because Internet servers are usually magnitudes more powerful than a client that receive their messages, so they need to be careful not to overwhelm the client's capacity.

TCP(Transmission Control Protocol) ===> Delivery Guarantees. (Mostly used protocol in web).
UDP(User Datagram Protocol) ===> Data packets could be lost. (Mostly used in streaming live video.)

## IP(Internet Protocol) Addresses

Data packets on the internet are sent to Internet Protocol(IP) addresses, numbers assigned to individual internet-connected computers. Each IP address must be unique, so new IP addresses are issued in a structured fashion.

Highest Level Authority ===> ICANN(Internet Corporation for Assigned Names and Numbers)
Regional Authorities ===> Grants the blocks of addresses.
ISPs and Hosting Companies ===> Provides IP addresses to each and every single computer, servers or mobile devices that are connected to the internet.

IP addresses are binary numbers, generally written in IP version 4(IPv4) syntax, which allows for 2^32 (4,294,967,296) addresses.

[Learn How Memory works](./02.1-HowMemoryWorks.md)

    - A computer gets its IP from either a DHCP server (dynamic IP) or through manual configuration (static IP).
    - The IP address is stored in the computer's network configuration settings.
    - IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses, with vastly different capacities.
    - The structure of IP addresses includes the network and host identifiers, which enable devices to be located and communicated with on a network.
        - Example: 192.168.1.1
            - The first part (192.168) could represent the network.
            - The second part (1.1) represents the host within that network.

### Types of IP Addresses

Public vs. Private IP Addresses

1. Public IP Address:

   - A public IP address is globally unique and can be accessed over the Internet.
   - It is assigned by Internet Service Providers (ISPs) to home routers or devices directly connected to the Internet.
   - Public IP addresses are routable on the Internet, meaning they can communicate with other public IP addresses.

2. Private IP Address:

   - A private IP address is used within local networks (e.g., home, office networks) and is not routable over the public Internet.
   - Devices in private networks use private IP addresses to communicate with each other. A router with Network Address Translation (NAT) translates these private IP addresses to a public IP address when communicating with the Internet.
   - Private IP ranges:
     - 10.0.0.0 – 10.255.255.255
     - 172.16.0.0 – 172.31.255.255
     - 192.168.0.0 – 192.168.255.255

<code>Loopback IP Address</code> - A loopback address is used to test the local network stack of a device. It allows a computer to send data to itself.

- IPv4 loopback address: 127.0.0.1
- IPv6 loopback address: ::1

### Structure of an IP Address

1. IPv4 Structure :: An IPv4 address is divided into two main parts:
   - Network Identifier (Network ID): The portion of the address that identifies the network on which the device is located.
   - Host Identifier (Host ID): The portion of the address that identifies the specific device (host) on the network.

The division between the network and host parts is determined by the subnet mask (or prefix length). For example, in the address 192.168.1.1/24, the first 24 bits (192.168.1) represent the network, and the last 8 bits (1) represent the host.

2. IPv6 Structure :: An IPv6 address is also divided into two parts:
   - Network Prefix: The first 64 bits of the address, representing the network.
   - Interface Identifier: The remaining 64 bits, identifying the specific device or interface on the network.

IPv6 addresses can be shortened by using double colons (::) to replace consecutive groups of zeros.

### Dynamic vs. Static IP addresses

1. Dynamic IP Address:

   - Most devices on home networks or enterprise networks are assigned dynamic IP addresses by a DHCP (Dynamic Host Configuration Protocol) server.
   - The address may change each time the device reconnects to the network or after a certain period.

2. Static IP Address:
   - A static IP address is manually assigned and remains constant over time.
   - Often used for servers, routers, or any device where a fixed IP address is necessary (e.g., web servers, email servers).

### Multicast and Broadcast IP Addresses

1. Multicast IP Address:

   - A multicast IP address is used to send data to multiple devices in a group.
   - For example, video streaming services often use multicast to send data to multiple recipients at once.
   - IPv4 multicast addresses range from 224.0.0.0 to 239.255.255.255.

2. Broadcast IP Address:
   - A broadcast address is used to send data to all devices on a local network.
   - In IPv4, the broadcast address for a subnet is the highest address in the network (e.g., 192.168.1.255 for a subnet 192.168.1.0/24).

### Subnetting and CIDR Notation

Subnetting allows dividing a larger network into smaller sub-networks, called subnets, which helps optimize IP address allocation and manage traffic efficiently. - Subnet Mask: A subnet mask is used to divide an IP address into the network and host portions. For example, 255.255.255.0 (or /24 in CIDR notation) indicates that the first 24 bits of the IP address are for the network, and the remaining bits are for the host. - CIDR (Classless Inter-Domain Routing) notation: Instead of using traditional subnet masks, CIDR uses a suffix after the IP address to indicate the number of bits in the network portion of the address. For example, 192.168.1.1/24.

### NAT (Network Address Translation)

Since public IPv4 addresses are limited, NAT is used to allow multiple devices on a private network to share a single public IP address. The router translates the private IP addresses into the public IP address for outgoing traffic and vice versa for incoming traffic.

### IP address in Binary format.

In the context of IP addresses, the bits are used to represent the numeric values of the address, which are then converted into more human-readable forms like dotted decimal notation for IPv4 or hexadecimal notation for IPv6.

1. IPv4 ===> 32 bit

   - Ex:- 192.168.1.1
     - Binary format :: 11000000.10101000.00000001.00000001

2. IPv6 ===> 128 bit (hexadecimal format (eight 16-bit blocks))
   - Ex:- 2001:0db8:85a3:0000:0000:8a2e:0370:7334
     - Binary format :: 00100000 00000001:00001101 10111000:10000101 10100011:00000000 00000000:00000000 00000000:10001010 00101110:00000011 01110000:01110011 00110100

<code>The number of bits determines how many unique IP addresses can exist. More bits allow for a greater number of addresses, which is why IPv6, with 128 bits, has far more addresses than IPv4.</code>

### <code>Classification of IP addresses</code>

IP addresses are categorized into different classes and types based on their intended use and range. Here's a breakdown of the IPv4 address classes and their corresponding IP ranges, along with some other important IP categories.

<code>1. IPv4 Address Classes:</code>

<pre>
Class & Format     IP Range            	    Default Subnet Mask	            Usage <br/>
Class A(01xxxxxx)  1.0.0.0 – 126.255.255.255	255.0.0.0 (8 bits)	    Large networks (e.g., ISPs)
Class B(10xxxxxx)  128.0.0.0 – 191.255.255.255	255.255.0.0 (16 bits)	Medium-sized networks (e.g., universities)
Class C(11xxxxxx)  192.0.0.0 – 223.255.255.255	255.255.255.0 (24 bits)	Small networks (e.g., private networks)
Class D(111xxxxx)  224.0.0.0 – 239.255.255.255	N/A	                    Multicasting
Class E(1111xxxx)  240.0.0.0 – 255.255.255.255	N/A	    Reserved for research and experimental use
</pre>

<code>Note: 127.0.0.0 to 127.255.255.255 is reserved for loopback addresses (typically 127.0.0.1).</code>

<code>2. Private IP Address Ranges:</code>

These are used for internal networks and are not routable on the public Internet.

<pre>
Class	        Private IP Range	                Usage
Class A	    10.0.0.0 – 10.255.255.255	            Large private networks
Class B	    172.16.0.0 – 172.31.255.255	            Medium private networks
Class C	    192.168.0.0 – 192.168.255.255	        Small private networks
</pre>

<code>3. Special IPv4 Addresses:</code>

<pre>
Category	    IP Range	                            Usage
Loopback	    127.0.0.0 – 127.255.255.255	        Testing local device (localhost)
Link-Local	    169.254.0.0 – 169.254.255.255	    Auto-configuration (APIPA)
Multicast	    224.0.0.0 – 239.255.255.255	        Used for multicasting (Class D)
Broadcast	    255.255.255.255	                    Broadcast to all devices in network
</pre>

<code>4. Public IP Addresses:</code>

Public IP addresses range from 1.0.0.0 to 223.255.255.255 (excluding private IP ranges), and are globally routable on the Internet.

<code>IPv6 Address Types (Overview):</code>

IPv6 addresses are not categorized into classes but have different types: - Global Unicast: Public, globally routable addresses (2000::/3). - Link-Local: Used for communication within a local network (fe80::/10). - Multicast: Addresses for multicasting (ff00::/8). - Loopback: Used to refer to the local machine (::1).

### Total number of Hosts in each class.

IP address format :: 255.255.255.255

1. Class-A ===> Subnet mask ===> 8-bit(First octets)

   - Range :: 1-126
     - Total networks ===> 126
     - Total hosts in each network ===> 256*256*256 ===> 16,777,216
     - Total hosts in Class-A network ===> 16,777,216 \* 126 ===> 2,113,929,216 Hosts

2. Class-B ===> Subnet mask ===> 16-bit(First and second octets)

   - Range :: 128-191
     - Total networks
       - From first octets :: (191-128+1) ===> 64
       - From second octets :: 256
       - Total networks ===> 256 \* 64 ===> 16,384
     - Total hosts in each network ===> 256\*256 ===> 65,536
     - Total hosts in Class-B network ===> 16,384\*65,536 ===> 1,073,741,824 Hosts

3. Class-C ===> Subnet mask ===> 24-bits(First, second, and third octets)

   - Range :: 192-223
     - Total networks
       - From first octets :: (223-192+1) ===> 32
       - From second octets :: 256
       - From third octets :: 256
       - Total networks ===> 32 _ 256 _ 256 ===> 2,097,152
     - Total hosts in each network ===> 256
     - Total hosts in Class-C network ===> 2,097,152 \* 256 ===> 536,870,912 Hosts

4. Class-D ===> Subnet mask ===> 0-bit

   - Note: Class D is used for multicast addresses and does not have hosts. Class D addresses are not used for host-to-host communication, so they don’t count towards the total number of usable IP addresses.

5. Class-E ===> Subnet mask ===> 0-bit

   - Note: Class E is reserved for future use and experimental purposes. It is not used for general addressing, so it also doesn’t count towards the total number of usable IP addresses.

6. Loopback Network ===> Subnet mast ===> 0-bit
   - Range :: 127.0.0.0 upto 127.255.255.255
     - Total networks
       - From first octets :: 1
     - Total hosts ===> 256*256*256 ===> 16,777,216 Hosts
     - Total hosts in Loopback Network ===> 1 \* 16,777,216 ===> 16,777,216 Hosts
   - Note: The loopback range is used for testing within the local machine and does not count towards the global address space.

<code>Total Usable IP Addresses (excluding reserved and non-host ranges) :: ===> (2,113,929,216 + 1,073,741,824 + 536,870,912) ===> 3,724,541,952 Hosts (IP ADDRESSES)</code>

<code>
<pre>
- Total IP Addresses ===> 4,261,412,864 + 16,777,216 ===> 4,278,190,080
- Possible IP addresses ===> 256*256*256*256 ===> 4,294,967,296
- Remaining Addresses :: ===> 4,294,967,296−3,724,541,952 ===> 570,425,344
</pre>
</code>

TODO ===> In the counting of usable IP address needs improvement.

## APPLICATION LAYER PROTOCOL

TCP allows two computers to reliably exchange data on the internet, but it doesn't dictate how the data being sent should be interpreted. For that to happen, both computers need to agree to exchange information through another, hight levell-protocol in the suite.

Protocols that build on top of TCP (or UDP) are called _"application level protocols"_.

The lower-level protocols of the internet protocol suite provide basic data routing over a network, while the higher-level protocols in the application layer provide more structure for applications exchanging data.

### _Different layers with protocols_

_application layer_ ===> DNS, FTP, HTTP, IMAP(internet message access protocol), POP(post office protocol), SMTP, SSH, XMPP(extensible messaging and presence protocol) ===> (instant messaging)
_transport layer_ ===> TCP, UDP
_internet layer_ ===> IPv4, IPv6
_network layer_ ===> ARP(address resolution protocol), MAC(media access control), NDP(neighbor discovery protocol), OSPF(open shortest path first), PPP(point-to-point protocol)

_Web servers use the HTTP(Hyper text transfer protocol) to transport web pages and their resources to user agents such as web browsers._

### Flow of request

User agent ===> Request(for particular resources) ===> Server intercept the request ===> Send the resources (statusCode, message, data-requested data).

### HTTP Requests

An HTTP request sent by a browser consists of the following elements:

- _METHOD_ ===> GET, POST, PATCH, DELETE
- _URL_ ===> Address of that particular resource which is available on the internet.
- _HEADERS_ ===> Metadata(data about data)
- _BODY_ ===> Optional component contains any extra data that needs to be sent to the server.

### HTTP Response

An HTTP response sent by the server to the user agent which includes:

- _PROTOCOL DESCRIPTION_ ===> Ex :- HTTP/1.1
- _STATUS CODE_ ===> To know what happens with the request
- _STATUS MESSAGE_ ===> Request was understood, accepted, and responded
- _HTTP HEADERS_ ===> Metadata(data about data)
- _RESPONSE / REQUESTED RESOURCES_ ===> Actual data

### Status Code

100 - 199 ===> Informational
200 - 299 ===> Success
300 - 399 ===> Redirection
400 - 499 ===> Client side error
500 - 599 ===> Server side error

## Stateful Connections

State means any stored _data_.

When a user agents hits a request to a particular web server and the server respond back with some sort of data that event is called as a connection. So, what does it mean by stateful connection? Lets understand.

Web servers typically deal with many user agents at once, but HTTP does nothing to distinguish which requests are coming from which user agent. This wasn't an important consideration in the early days of the internet, because web pages were largely read-only. But, Modern websites, however, often allow users to log in and will track their activity as they visit and interact with different pages.

A connection or conversation between a client and a server is stateful when they perform a _"handshake"_ and continue to send packets back and forth until one of the communicating parties decides to terminate the connection.

When a web server wants to keep track of which user it's responding to with each request, and thus achieve a stateful HTTP conversation, it needs to establish a mechanism to track the user agent as it makes the subsequent requests.

The entire conversation between a particular user agent and a web server is called an HTTP session. The most common way of tracking sessions is for the server to send abck a _Set-Cookie_ header in the initial HTTP response.

Now, whenever the user agent makes subsequent request it also sends the cookie that server has given to them for _authentication_ and the session will not disconnect or expire until the user explicitly logout or cookie get expired.

### FLOW

User agent ===> 1st request to the server <=== Server send a Cookie in Set-Cookie header ===> User agent store the cookie in their cookie storage area.

User agent (with subsequent request) ===> Sends Payload(optional), The Cookie ===> Server use the cookie for authentication and verify the user agent or the user who is logged in.

Cookie Expired / Explicitly logged out ===> User needs to signin again ===> Server will generate a new cookie and it to the user agent along with the appropriate data.

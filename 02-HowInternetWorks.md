# How the Internet works?

This is the crucial stage for any web security engineers to understand the basics and underlying concepts of web technologies and its' protocols. We must have knowledge about how computers exchange data over the web.

PREDECESSOR OF THE INTERNET ===> ARPANET (Advanced Research Projects Agency Network).

## TCP(Transmission Control Protocol).

The first message sent over the "ARPANET" was a LOGIN command destined for a remote computer at Stanford University. The network sent the first two letters, <code>LO</code> and then crashed. This was a problem for US military, which was looking for a way to connect remote computers so that they could continue to exchange information at any situation.

To address this problem, the network engineers developed the "Transmission Control Protocol(TCP)" to ensure a reliable exchange of information between computers.

## How data travels on the Internet?

When a computer sends a message to another machine via TCP, the message is split into data packets that are send towards their eventual destination with a destination address. If the recipient fails to acknowledge receipt of a packet, the sender resends that packet, possibly along a different network path. In this way, TCP allows computers to deliver data across a network that is expected to be unreliable.

TCP has undergone significant improvements as the internet has grown. Packets are now send with a "checksum" that allows recipients to detect data corruption and determine whether packetes need to be resent.

Sendersa also preemptively adjust the rate at which they send data according to how fast it's being consumed. Because Internet servers are usually magnitudes more powerful than a client that receive their messages, so they need to be careful not to overwhelm the client's capacity.

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

Subnetting allows dividing a larger network into smaller sub-networks, called subnets, which helps optimize IP address allocation and manage traffic efficiently.
    - Subnet Mask: A subnet mask is used to divide an IP address into the network and host portions. For example, 255.255.255.0 (or /24 in CIDR notation) indicates that the first 24 bits of the IP address are for the network, and the remaining bits are for the host.
    - CIDR (Classless Inter-Domain Routing) notation: Instead of using traditional subnet masks, CIDR uses a suffix after the IP address to indicate the number of bits in the network portion of the address. For example, 192.168.1.1/24.

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

Class	        IP Range            	    Default Subnet Mask	            Usage <br/>
Class A	        1.0.0.0 – 126.255.255.255	255.0.0.0 (8 bits)	    Large networks (e.g., ISPs)
<br/>
Class B	        128.0.0.0 – 191.255.255.255	255.255.0.0 (16 bits)	Medium-sized networks (e.g., universities)
<br/>
Class C	        192.0.0.0 – 223.255.255.255	255.255.255.0 (24 bits)	Small networks (e.g., private networks)
<br/>
Class D	        224.0.0.0 – 239.255.255.255	N/A	                    Multicasting
<br/>
Class E	        240.0.0.0 – 255.255.255.255	N/A	    Reserved for research and experimental use
<br/>
<code>Note: 127.0.0.0 to 127.255.255.255 is reserved for loopback addresses (typically 127.0.0.1).</code>

<code>2. Private IP Address Ranges:</code>

These are used for internal networks and are not routable on the public Internet.

Class	        Private IP Range	                Usage<br/>
Class A	    10.0.0.0 – 10.255.255.255	            Large private networks<br/>
Class B	    172.16.0.0 – 172.31.255.255	            Medium private networks<br/>
Class C	    192.168.0.0 – 192.168.255.255	        Small private networks<br/>

<code>3. Special IPv4 Addresses:</code>

Category	    IP Range	                            Usage<br/>
Loopback	    127.0.0.0 – 127.255.255.255	        Testing local device (localhost)<br/>
Link-Local	    169.254.0.0 – 169.254.255.255	    Auto-configuration (APIPA)<br/>
Multicast	    224.0.0.0 – 239.255.255.255	        Used for multicasting (Class D)<br/>
Broadcast	    255.255.255.255	                    Broadcast to all devices in network<br/>

<code>4. Public IP Addresses:</code>

Public IP addresses range from 1.0.0.0 to 223.255.255.255 (excluding private IP ranges), and are globally routable on the Internet.

<code>IPv6 Address Types (Overview):</code>

IPv6 addresses are not categorized into classes but have different types:
    - Global Unicast: Public, globally routable addresses (2000::/3).
    - Link-Local: Used for communication within a local network (fe80::/10).
    - Multicast: Addresses for multicasting (ff00::/8).
    - Loopback: Used to refer to the local machine (::1).

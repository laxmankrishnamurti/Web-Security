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

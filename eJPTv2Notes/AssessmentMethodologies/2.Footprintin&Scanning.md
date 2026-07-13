<img width="953" height="426" alt="image" src="https://github.com/user-attachments/assets/b5256ea3-7ff6-4da1-bcfc-248c42c2297f" />
<img width="953" height="499" alt="image" src="https://github.com/user-attachments/assets/942212ac-1d67-4ea6-9253-a8017b95eba1" />


# Network Protocols

In computer networks, hosts communicate with each other through the use of **network protocols**. These protocols ensure that different computer systems, using different hardware and software, can communicate effectively with one another.

There are a large number of network protocols used by different services, each designed for specific objectives and functionalities.

### Key Points

- Enable communication between devices on a network
- Define rules for data transmission and reception
- Ensure interoperability between different hardware and software platforms
- Support various network services and applications

---

# Packets

The primary goal of networking is the exchange of information between networked computers. This information is transferred in the form of **packets**.

Packets are streams of bits transmitted as electrical or wireless signals over physical media used for data transmission, such as:

- Ethernet
- Wi-Fi
- Fiber Optic Cables
- Cellular Networks

These signals are interpreted as binary data (**0s and 1s**) that make up the information being exchanged between devices.

### Key Points

- Packets are the basic units of data transmission
- Data is broken into packets before being sent across a network
- Packets travel through various network devices before reaching their destination
- The receiving device reassembles the packets into the original data

---

# The OSI Model

The **OSI (Open Systems Interconnection) Model** is a conceptual framework that standardizes the functions of a telecommunication or computing system into **seven abstraction layers**.

It was developed by the **International Organization for Standardization (ISO)** to facilitate communication between different systems and devices, ensuring interoperability across a wide range of networking technologies.

The OSI model divides network communication into seven layers, with each layer responsible for a specific function.

## Purpose of the OSI Model

- Standardizes network communication processes
- Promotes interoperability between different systems and vendors
- Simplifies troubleshooting by separating functions into layers
- Provides a structured approach to network design and implementation

## The Seven Layers of the OSI Model

| Layer | Name | Function |
|---------|---------|---------|
| 7 | Application | Provides network services to end-user applications |
| 6 | Presentation | Translates, encrypts, and compresses data |
| 5 | Session | Establishes, manages, and terminates communication sessions |
| 4 | Transport | Ensures reliable data transfer between systems |
| 3 | Network | Handles routing and logical addressing |
| 2 | Data Link | Provides node-to-node data transfer and error detection |
| 1 | Physical | Transmits raw bits over physical media |


<img width="960" height="485" alt="image" src="https://github.com/user-attachments/assets/5f734e24-52c6-4950-b001-d52037e6393b" />

## Important Note

> The OSI model is not a strict blueprint for every networking system. Instead, it serves as a reference model that helps professionals understand, design, and troubleshoot network architectures by organizing complex communication processes into manageable layers.


# Network Layer (Layer 3)

The **Network Layer (Layer 3)** of the OSI model is responsible for **logical addressing, routing, and forwarding data packets** between devices across different networks.

Its primary goal is to determine the most efficient path for data to travel from the source to the destination, even when the devices are located on separate networks.

The Network Layer abstracts the underlying physical infrastructure, allowing different networks to communicate as a unified internetwork.

## Common Network Layer Protocols

The following protocols operate at the Network Layer:

- Internet Protocol (IP)
- Internet Control Message Protocol (ICMP)

---

# Internet Protocol (IP)

**Internet Protocol (IP)** is a core protocol of the Internet and operates at **Layer 3 (Network Layer)** of the OSI model.

It is responsible for:

- Logical addressing
- Routing
- Packet forwarding
- Fragmentation and reassembly

IP enables communication between devices on different networks by providing a standardized method for identifying and locating hosts.

---

## IP Versions

### IPv4

IPv4 is the most widely used version of the Internet Protocol and uses **32-bit addresses**.

#### Example

```text
192.168.0.1
```

### IPv6

IPv6 was developed to address the limitations of IPv4 and provides a much larger address space using **128-bit addresses**.

#### Example

```text
2001:0db8:85a3:0000:0000:8a2e:0370:7334
```

---

## Logical Addressing

IP addresses serve as logical identifiers assigned to network interfaces.

### Key Points

- Uniquely identify devices on a network
- Enable communication between hosts
- Organized using network classes, subnets, and CIDR notation
- Used by routers to determine packet destinations

---

## Packet Structure

IP organizes data into packets before transmission.

Each IP packet consists of:

### Header

Contains control information such as:

- Source IP Address
- Destination IP Address
- IP Version
- Time To Live (TTL)
- Protocol Type
- Header Length

### Payload

Contains the actual data being transmitted.

---

## Fragmentation and Reassembly

When a packet is larger than the maximum transmission size supported by a network, IP can divide it into smaller fragments.

### Process

1. The sender or router fragments the packet.
2. Fragments travel independently across the network.
3. The receiving host reassembles the fragments.
4. The original packet is reconstructed.

### Benefits

- Allows transmission across networks with different MTU (Maximum Transmission Unit) sizes.
- Improves compatibility between different network technologies.

---

## IP Addressing Types

IP communication can be categorized into three addressing methods:

### Unicast

**One-to-One Communication**

A packet is sent from one sender to one specific receiver.

#### Example

```text
PC-A → PC-B
```

### Broadcast

**One-to-All Communication**

A packet is sent to all devices within a subnet.

#### Example

```text
192.168.1.255
```

### Multicast

**One-to-Many Communication**

A packet is sent to a selected group of devices that have joined a multicast group.

#### Example

```text
Streaming video to multiple subscribers
```

---

## Subnetting

Subnetting is the process of dividing a large network into smaller, more manageable subnetworks.

### Benefits of Subnetting

- Improved network performance
- Reduced broadcast traffic
- Better security
- Easier network management
- More efficient IP address utilization

---

# Internet Control Message Protocol (ICMP)

**Internet Control Message Protocol (ICMP)** works alongside IP and is primarily used for:

- Error reporting
- Network diagnostics
- Connectivity testing

### Common ICMP Messages

| Message Type | Purpose |
|-------------|---------|
| Echo Request | Sent by the `ping` utility |
| Echo Reply | Response to an Echo Request |
| Destination Unreachable | Indicates a routing or connectivity problem |
| Time Exceeded | Indicates that the TTL value has expired |

### Example

```bash
ping google.com
```

The `ping` utility uses ICMP Echo Requests and Echo Replies to verify connectivity between hosts.

---

# Dynamic Host Configuration Protocol (DHCP)

**Dynamic Host Configuration Protocol (DHCP)** is commonly used alongside IP to automatically assign network configuration information to devices.

### DHCP Automatically Assigns

- IP Address
- Subnet Mask
- Default Gateway
- DNS Server Addresses

### Benefits

- Simplifies network administration
- Reduces manual configuration errors
- Efficiently manages IP address allocation

---

# IP Header Format

The IP protocol defines multiple fields within the packet header.

These fields contain binary values that IPv4 devices and services use to process and forward packets across a network.

## Common IPv4 Header Fields

| Field | Description |
|---------|-------------|
| Version | Identifies the IP version (IPv4 or IPv6) |
| Header Length | Size of the header |
| Type of Service (ToS) | Quality of Service information |
| Total Length | Total packet size |
| Identification | Used for packet fragmentation |
| Flags | Controls fragmentation |
| Fragment Offset | Position of a fragment within the original packet |
| Time To Live (TTL) | Limits packet lifetime |
| Protocol | Specifies the upper-layer protocol (TCP, UDP, ICMP, etc.) |
| Header Checksum | Error detection for the header |
| Source Address | Sender's IP address |
| Destination Address | Receiver's IP address |

> These header fields allow routers and hosts to correctly route, process, and deliver packets across interconnected networks.

<img width="889" height="307" alt="image" src="https://github.com/user-attachments/assets/78bbaea4-c6ea-4b27-b12f-edbb2f55e540" />
<img width="773" height="312" alt="image" src="https://github.com/user-attachments/assets/b162e9eb-0d09-4f76-8daa-8a244e458280" />
<img width="766" height="331" alt="image" src="https://github.com/user-attachments/assets/5b50793d-0858-4d35-a31b-92c54107ffb8" />
<img width="763" height="303" alt="image" src="https://github.com/user-attachments/assets/ad1dfaa0-5ef4-4f8e-81c8-f2a8b09fc552" />


# Transport Layer (Layer 4)

The **Transport Layer (Layer 4)** is the fourth layer of the OSI model and plays a critical role in enabling communication between devices across a network.

This layer is responsible for providing **end-to-end communication** and ensuring the reliable and orderly delivery of data between two devices.

## Functions of the Transport Layer

The Transport Layer performs several important tasks, including:

- End-to-end communication
- Error detection and recovery
- Flow control
- Data segmentation and reassembly
- Reliable data delivery
- Ordered data transmission

---

# Transport Layer Protocols

The two primary protocols that operate at the Transport Layer are:

- Transmission Control Protocol (TCP)
- User Datagram Protocol (UDP)

---

# Transmission Control Protocol (TCP)

**Transmission Control Protocol (TCP)** is a connection-oriented protocol that provides reliable and ordered delivery of data between devices on a network.

TCP ensures that data sent from one application is received accurately and in the correct order by another application.

## Key Features of TCP

### Connection-Oriented

TCP establishes a connection between the sender and receiver before any data is transmitted.

This connection acts as a virtual communication channel that ensures reliable data transfer.

#### Process

1. Connection establishment
2. Data transmission
3. Connection termination

---

### Reliability

TCP guarantees reliable delivery of data.

It achieves reliability through:

- Acknowledgments (ACKs)
- Sequence numbers
- Error detection
- Retransmission of lost packets

If a segment is lost or corrupted during transmission, TCP automatically retransmits it.

---

### Ordered Data Transfer

TCP ensures that data is delivered in the correct order.

If packets arrive out of sequence:

1. TCP stores them temporarily.
2. Reorders them correctly.
3. Delivers them to the application in the proper sequence.

This guarantees data integrity and consistency.

---

### Common Uses of TCP

TCP is commonly used by applications that require reliable communication, such as:

- Web Browsing (HTTP/HTTPS)
- Email (SMTP, IMAP, POP3)
- File Transfers (FTP, SFTP)
- Remote Access (SSH)

---

# User Datagram Protocol (UDP)

**User Datagram Protocol (UDP)** is a connectionless protocol that focuses on speed and efficiency.

Unlike TCP, UDP does not establish a connection before transmitting data and does not guarantee reliability or ordered delivery.

## Key Features of UDP

### Connectionless Communication

UDP sends data without first establishing a connection between the sender and receiver.

This reduces overhead and improves transmission speed.

---

### Faster Data Transmission

Because UDP does not perform:

- Connection establishment
- Acknowledgments
- Retransmissions
- Sequence tracking

it is generally much faster than TCP.

---

### No Reliability Guarantees

UDP does not guarantee:

- Packet delivery
- Packet order
- Error recovery

If a packet is lost during transmission, UDP does not attempt to resend it.

---

### Independent Packets

Each UDP packet (datagram) is treated independently.

A UDP packet has no relationship with previous or future packets.

As a result:

- Packets may arrive out of order
- Packets may be duplicated
- Packets may be lost

---

### Common Uses of UDP

UDP is commonly used in applications where speed is more important than reliability, including:

- Video Streaming
- Voice over IP (VoIP)
- Online Gaming
- DNS Queries
- Live Broadcasts

---

# TCP vs UDP

| Feature | TCP | UDP |
|----------|-----|-----|
| Connection Type | Connection-Oriented | Connectionless |
| Reliability | Reliable | Unreliable |
| Data Ordering | Guaranteed | Not Guaranteed |
| Error Recovery | Yes | No |
| Speed | Slower | Faster |
| Acknowledgments | Yes | No |
| Retransmission | Yes | No |
| Overhead | Higher | Lower |
| Common Uses | Web, Email, File Transfer | Streaming, Gaming, DNS |

---

# Summary

The **Transport Layer (Layer 4)** is responsible for end-to-end communication between devices and applications.

The two primary Transport Layer protocols are:

- **TCP** — Reliable, connection-oriented, and ordered communication.
- **UDP** — Fast, lightweight, and connectionless communication.

Choosing between TCP and UDP depends on the requirements of the application, specifically whether **reliability** or **speed** is the higher priority.

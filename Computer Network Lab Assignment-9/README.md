# Experiment 9: Transport Layer Simulation – UDP, TCP, and SCTP Comparison

---

## Aim

To implement a transport layer simulation demonstrating process-to-process communication using UDP, TCP, and SCTP protocols, and to compare them in terms of connection establishment, data transmission, and congestion control using Cisco Packet Tracer.

---

## Objective

- Understand how the transport layer enables process-to-process communication.
- Simulate and observe UDP and TCP packet transmission in Cisco Packet Tracer.
- Compare the behavior of UDP, TCP, and SCTP protocols across key parameters.
- Analyze connection setup, reliability, ordering, and congestion control mechanisms for each protocol.

---

## Theory

The **Transport Layer** (Layer 4 of the OSI model) is responsible for end-to-end communication between processes running on different hosts. It uses **port numbers** to identify processes and offers two primary delivery models:

### TCP (Transmission Control Protocol)
A **connection-oriented** protocol that guarantees reliable, ordered delivery of data. It uses a **3-way handshake** (SYN → SYN-ACK → ACK) before transmission begins. TCP supports acknowledgments (ACK), retransmission of lost packets, flow control, and congestion control — making it ideal for applications like web browsing and file transfer.

### UDP (User Datagram Protocol)
A **connectionless** protocol that sends data without establishing a connection or guaranteeing delivery. There are no acknowledgments, no retransmissions, and no ordering. Its low overhead makes it suitable for real-time applications like video streaming, VoIP, and online gaming.

### SCTP (Stream Control Transmission Protocol)
A **connection-oriented** protocol that combines features of both TCP and UDP. It uses a **4-way handshake** (INIT → INIT-ACK → COOKIE-ECHO → COOKIE-ACK) and supports **multi-streaming** (multiple data streams within one connection) and **multi-homing** (multiple IP paths for redundancy), making it well-suited for telecom signaling.

---

## Step-by-Step Procedure

### Step 1: Setup the Network Environment

1. Open **Cisco Packet Tracer** and create a new project.
2. Add the following devices from the device panel:
   - `PC0` and `PC1` (End devices)
   - `Switch0` (Cisco 2960)
3. Connect devices using **Copper Straight-Through** cables:
   - `PC0` → `Switch0`
   - `PC1` → `Switch0`

### Step 2: Configure IP Addresses

1. Click on `PC0` → go to **Desktop** tab → **IP Configuration**.
2. Set the following:
   - IP Configuration: **Static**
   - IPv4 Address: `192.168.1.12`
   - Subnet Mask: `255.255.255.0`
   - Default Gateway: `0.0.0.0`
3. Repeat for `PC1`:
   - IPv4 Address: `192.168.1.13`
   - Subnet Mask: `255.255.255.0`

### Step 3: Test Connectivity

1. Click on `PC0` → **Desktop** → **Command Prompt**.
2. Run the ping command to verify connectivity:
   ```
   ping 192.168.1.13
   ```
3. Confirm 0% packet loss in the ping statistics output.

### Step 4: Simulate UDP Communication

1. Switch to **Simulation Mode** (bottom-right toggle).
2. In the Event List Filters, ensure **UDP** is selected under visible events.
3. Click **Add Simple PDU** (envelope icon).
4. Click `PC0` as source, then `PC1` as destination.
5. Click **Play** to observe packet flow across the network.
6. Note in the Event List that packets travel directly without any handshake.

### Step 5: Simulate TCP Communication

1. Reset simulation and create a new scenario if needed.
2. Open **Event List Filters** → enable **TCP** events.
3. Use **Add Complex PDU** or a web/FTP service to trigger TCP traffic.
4. Click **Play** and observe the 3-way handshake (SYN, SYN-ACK, ACK) in the simulation panel.
5. Track packet events through `PC0 → Switch0 → PC1`.

---

## Configuration Commands

> Cisco Packet Tracer simulates configuration via GUI. The equivalent CLI commands for IP assignment on the PC interfaces are shown below for reference.

**PC0 – IP Configuration (via CLI equivalent):**
```
ip address 192.168.1.12 255.255.255.0
```

**PC1 – IP Configuration (via CLI equivalent):**
```
ip address 192.168.1.13 255.255.255.0
```

**Ping Command (tested from PC0 Command Prompt):**
```
ping 192.168.1.13
```

**Connectivity output observed:**
```
Pinging 192.168.1.13 with 32 bytes of data:
Reply from 192.168.1.13: bytes=32 time<1ms TTL=128
Reply from 192.168.1.13: bytes=32 time<1ms TTL=128
Reply from 192.168.1.13: bytes=32 time<1ms TTL=128
Reply from 192.168.1.13: bytes=32 time<1ms TTL=128

Ping statistics for 192.168.1.13:
    Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
Approximate round trip times in milli-seconds:
    Minimum = 0ms, Maximum = 0ms, Average = 0ms
```

---

## Observations / Results

### Ping Test Result

| Parameter          | Value               |
|--------------------|---------------------|
| Source IP          | 192.168.1.12 (PC0)  |
| Destination IP     | 192.168.1.13 (PC1)  |
| Packets Sent       | 4                   |
| Packets Received   | 4                   |
| Packet Loss        | 0%                  |
| Round Trip Time    | 0ms (min/max/avg)   |

### Protocol Comparison Table

| Feature               | TCP                         | UDP                        | SCTP                             |
|-----------------------|-----------------------------|----------------------------|----------------------------------|
| Connection Type       | Connection-oriented         | Connectionless             | Connection-oriented              |
| Handshake             | 3-way (SYN/SYN-ACK/ACK)    | None                       | 4-way (INIT/INIT-ACK/COOKIE)    |
| Reliability           | Guaranteed delivery         | No guarantee               | Guaranteed delivery              |
| Data Ordering         | Maintained                  | Not maintained             | Maintained (per stream)          |
| Acknowledgments (ACK) | Yes                         | No                         | Yes                              |
| Retransmission        | Yes                         | No                         | Yes                              |
| Flow Control          | Yes                         | No                         | Yes                              |
| Congestion Control    | Yes                         | No                         | Yes                              |
| Multi-streaming       | No                          | No                         | Yes                              |
| Multi-homing          | No                          | No                         | Yes                              |
| Overhead              | High                        | Low                        | Medium–High                      |
| Use Cases             | HTTP, FTP, Email            | DNS, VoIP, Streaming       | Telecom Signaling (SS7/SIGTRAN)  |

### Simulation Event Log – UDP

| Time (sec) | Last Device    | Event       |
|------------|----------------|-------------|
| 0.000      | —              | PDU Created |
| 0.001      | 192.168.1.12   | Sent        |
| 0.002      | Switch0        | Forwarded   |
| 0.003      | 192.168.1.13   | Received    |

> UDP packets were delivered without any connection setup. No ACK or handshake events were observed.

### Simulation Event Log – TCP

| Time (sec) | Last Device    | Event         |
|------------|----------------|---------------|
| 0.000      | —              | PDU Created   |
| 0.004      | —              | SYN Sent      |
| 0.005      | 192.168.1.12   | SYN-ACK Rcvd  |
| 0.006      | Switch0        | ACK Sent      |
| 0.007      | 192.168.1.13   | Data Transfer |
| 0.008      | Switch0        | ACK Confirmed |

> TCP packets followed a clear 3-way handshake before data transmission began. Delivery was confirmed via ACK.

---

## Conclusion

This experiment successfully demonstrated process-to-process communication at the transport layer using UDP and TCP in Cisco Packet Tracer, with SCTP analyzed for comparison.

- **UDP** was observed to be fast and lightweight but offered no reliability guarantees — packets were sent directly without any handshake or acknowledgment.
- **TCP** ensured reliable, ordered communication through its 3-way handshake, ACK mechanism, and retransmission capability, at the cost of higher overhead.
- **SCTP** extends TCP's reliability with multi-streaming and multi-homing support, making it suited for fault-tolerant and telecom-grade applications.

The ping test confirmed successful network setup with **0% packet loss**, and simulation mode validated correct packet flow across both protocols. This experiment reinforces the importance of selecting the right transport protocol based on the application's requirements for speed, reliability, and overhead tolerance.

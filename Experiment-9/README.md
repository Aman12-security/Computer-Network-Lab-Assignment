# Experiment 9: Transport Layer Simulation

## Problem Statement

Implement a transport layer simulation to demonstrate process-to-process communication using UDP, TCP, and SCTP protocols. Compare these protocols in terms of connection establishment, data transmission, and congestion control using Cisco Packet Tracer.

---

## Aim

Transport Layer Simulation: UDP, TCP, and SCTP Comparison

---

## Tools Required

- Cisco Packet Tracer

---

## Procedure

### Step 1: Setup the Network Environment

1. Open Cisco Packet Tracer and create a new project.
2. Add the following devices:
   - Two PCs: `PC0` and `PC1`
   - One Switch: `2960`
3. Connect devices:
   - `PC0` → Switch
   - `PC1` → Switch
   - Use **Copper Straight-Through** cables for all connections.

### Step 2: Configure IP Addresses

Assign static IP addresses to both PCs:

| Device | IP Address    | Subnet Mask   |
|--------|---------------|---------------|
| PC0    | 192.168.1.12  | 255.255.255.0 |
| PC1    | 192.168.1.13  | 255.255.255.0 |

Steps:
1. Click on a PC → go to **Config** tab → **FastEthernet0**.
2. Set IP Configuration to **Static**.
3. Enter the IP address and subnet mask.
4. Repeat for the second PC.

### Step 3: Test Connectivity

1. Open **Command Prompt** on PC0.
2. Run the following ping command:
   ```
   ping 192.168.1.2
   ```
3. Successful replies (0% packet loss) confirm proper network setup.

---

## UDP Communication Simulation

1. Switch to **Simulation Mode** in Cisco Packet Tracer.
2. Select **Add Simple PDU** (envelope icon).
3. Click **PC0** as source and **PC1** as destination.
4. Observe the packet flow in the Event List panel.
5. Note that packets are sent without any connection setup (connectionless).

---

## TCP Communication Simulation

1. Open Cisco Packet Tracer and create a new project.
2. Add **2 PCs** and **1 Switch**, connect using copper straight-through cables.
3. Assign IP addresses:
   - PC0: `192.168.10.1 / 255.255.255.0`
   - PC1: `192.168.10.2 / 255.255.255.0`
   - PC2: `192.168.10.3 / 255.255.255.0`
4. Switch to **Simulation Mode**.
5. Observe packets and verify successful communication.

---

## Protocol Comparison

### TCP (Transmission Control Protocol)

| Feature | Description |
|---|---|
| Connection Type | Connection-oriented (connection established before transmission) |
| Reliability | Reliable — guarantees delivery |
| Data Order | Maintains correct order of data |
| Acknowledgments | Uses ACK packets |
| Lost Packets | Retransmits lost packets |
| Flow Control | Yes |
| Congestion Control | Yes |

### UDP (User Datagram Protocol)

| Feature | Description |
|---|---|
| Connection Type | Connectionless (no connection setup) |
| Reliability | Unreliable — no guarantee of delivery |
| Data Order | Does not maintain order |
| Acknowledgments | None |
| Lost Packets | No retransmission |
| Flow Control | No |
| Congestion Control | No |

### SCTP (Stream Control Transmission Protocol)

| Feature | Description |
|---|---|
| Connection Type | Connection-oriented (four-way handshake) |
| Reliability | Reliable — like TCP |
| Data Order | Supports ordered and unordered delivery |
| Multi-streaming | Yes — multiple streams in one association |
| Multi-homing | Yes — supports multiple IP addresses |
| Congestion Control | Yes |

---

## Key Takeaways

- **TCP** is best suited for applications requiring reliability and ordered delivery (e.g., file transfer, web browsing).
- **UDP** is preferred for low-latency, time-sensitive applications where some data loss is acceptable (e.g., video streaming, online gaming, VoIP).
- **SCTP** combines benefits of both TCP and UDP, offering reliability with multi-streaming and multi-homing support, making it ideal for signaling protocols in telecom networks.

# 🌐 IPv4, IPv6 and Address Mapping Simulation


# 📖 1. Objective

The objective of this assignment is to simulate **logical addressing using IPv4 and IPv6** and demonstrate address mapping techniques such as **ARP, RARP, BOOTP, and DHCP**. The simulation visualizes how devices acquire and resolve network addresses.

---

# 🧠 2. Concepts Covered

* IPv4 Addressing
* IPv6 Addressing
* ARP (Address Resolution Protocol)
* RARP (Reverse ARP)
* BOOTP (Bootstrap Protocol)
* DHCP (Dynamic Host Configuration Protocol)

---

# 🏗️ 3. Network Topology

The network consists of:

* 2 PCs
* 1 Server (DHCP, BOOTP, RARP)
* 1 Router
* 1 Switch

### 🔹 Logical Diagram

```id="topo3"
PC0 ----\
         \
          SWITCH ---- ROUTER ---- SERVER
         /
PC1 ----/
```
<img width="515" height="505" alt="Screenshot_2026-04-23_10-37-31" src="https://github.com/user-attachments/assets/e8bd4ec9-3bda-4885-9ab6-adea07ce3354" />

---

# 🔌 4. Network Configuration

## 📍 IPv4 Addressing (Static)

| Device | IPv4 Address |
| ------ | ------------ |
| PC0    | 192.168.1.2  |
| PC1    | 192.168.1.3  |
| Router | 192.168.1.1  |
| Server | 192.168.1.10 |

---

## 📍 IPv6 Addressing

| Device | IPv6 Address   |
| ------ | -------------- |
| PC0    | 2001:db8:1::2  |
| PC1    | 2001:db8:1::3  |
| Router | 2001:db8:1::1  |
| Server | 2001:db8:1::10 |

---

# 🔄 5. Address Mapping Techniques

---

## 🟡 ARP (Address Resolution Protocol)

### 🔹 Implementation

* Ping executed from PC0 to PC1

### 🔹 Observation

* ARP request broadcast sent
* ARP reply received with MAC address

---

## 🔁 RARP (Reverse ARP)

### 🔹 Implementation

* RARP service enabled on server
* MAC-to-IP mappings configured

### 🔹 Observation

* Client requested IP using MAC
* Server responded with IP address

---

## 🔵 BOOTP

### 🔹 Implementation

* BOOTP service enabled on server
* Static IP mappings configured

### 🔹 Observation

* Client requested IP
* Server assigned predefined IP

---

## 🟢 DHCP

### 🔹 Implementation

* DHCP service enabled on server
* IP pool configured

### 🔹 Observation

* DHCP Discover
* DHCP Offer
* DHCP Request
* DHCP Acknowledgment

---

# 🌐 6. IPv4 and IPv6 Communication

* Successful ping using IPv4
* Successful ping using IPv6
* Verified dual-stack communication

---

# 🔍 7. Simulation and Visualization

Using Simulation Mode:

* Observed ARP packets
* Tracked DHCP handshake
* Monitored ICMP communication
* Analyzed packet-level details

---

# 📊 8. Comparison of Techniques

| Protocol | Function      | Dynamic | Usage           |
| -------- | ------------- | ------- | --------------- |
| ARP      | IP → MAC      | No      | Local network   |
| RARP     | MAC → IP      | No      | Legacy          |
| BOOTP    | IP assignment | Limited | Boot devices    |
| DHCP     | Dynamic IP    | Yes     | Modern networks |

---

# 📊 9. Observations

* ARP resolved MAC addresses successfully
* DHCP dynamically assigned IP addresses
* BOOTP assigned static predefined IPs
* RARP demonstrated reverse mapping conceptually
* IPv6 communication worked alongside IPv4

---

# ⚠️ 10. Challenges Faced

* Limited support for RARP in simulation
* Configuring multiple services on server
* Understanding packet flow in Simulation Mode

---

# 🚀 11. Improvements

* Add DNS integration
* Simulate larger networks
* Explore IPv6 DHCP (DHCPv6)
* Analyze network performance under load

---

# 🧾 12. Conclusion

The simulation successfully demonstrated logical addressing and address mapping techniques. IPv4 and IPv6 communication were verified, and protocols like ARP and DHCP played a crucial role in address resolution and allocation.

---

# ▶️ 13. How to Run

1. Open `.pkt` files in Cisco Packet Tracer
2. Verify all configurations
3. Use ping and DHCP settings
4. Switch to Simulation Mode
5. Observe packet flow

---

# 📁 14. Files Included

* `ipv4_ipv6_addressing.pkt`
* `address_mapping.pkt`
* `README.md`
* `output.txt`
* `test_cases.txt`

---

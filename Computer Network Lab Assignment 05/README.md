# 🌐 Flow Control and Error Control Protocols Simulation

*(Stop-and-Wait, Go-Back-N ARQ, Selective Repeat ARQ)*


# 📖 1. Objective

The objective of this assignment is to simulate and analyze **flow control and error control protocols** including **Stop-and-Wait**, **Go-Back-N ARQ**, and **Selective Repeat ARQ**. The simulation demonstrates how data transmission reliability and efficiency are managed under different network conditions.

---

# 🧠 2. Concepts Covered

* Flow Control Mechanisms
* Error Control Protocols
* Stop-and-Wait ARQ
* Go-Back-N ARQ
* Selective Repeat ARQ
* Packet Loss and Retransmission

---

# 🏗️ 3. Network Topology

A simple LAN topology was used to focus purely on protocol behavior:

* 2 PCs (Sender and Receiver)
* 1 Switch

### 🔹 Logical Diagram

```
PC0 -------- SWITCH -------- PC1
(Sender)                  (Receiver)
```

---

# 🔌 4. Network Configuration

## 📍 IP Addressing

| Device | IP Address  | Subnet Mask   |
| ------ | ----------- | ------------- |
| PC0    | 192.168.1.1 | 255.255.255.0 |
| PC1    | 192.168.1.2 | 255.255.255.0 |

---

## 🔗 Cabling

* Devices connected using **Copper Straight-Through cables**
* Switch used for communication

---

# ⚙️ 5. Simulation Methodology

All simulations were performed using **Cisco Packet Tracer** in **Simulation Mode**.

### 🔹 Common Steps

1. Switched to Simulation Mode
2. Enabled only **ICMP** in filters
3. Used **Add Simple PDU** for packet generation
4. Used **Capture/Forward** to observe flow
5. Simulated errors by deleting packets in Event List

---

# 🟡 6. Stop-and-Wait ARQ

### 🔹 Implementation

* Sent one packet at a time
* Waited for acknowledgment before sending next

### 🔍 Observations

* Only one frame in transit
* On packet loss → only that packet retransmitted

### 📌 Conclusion

* Simple but inefficient
* Low throughput due to waiting

---

# 🔵 7. Go-Back-N ARQ

### 🔹 Implementation

* Sent multiple packets continuously
* Did not wait for individual acknowledgments

### 🔍 Observations

* On packet loss → receiver discarded subsequent packets
* Sender retransmitted multiple packets from error point

### 📌 Conclusion

* Better throughput than Stop-and-Wait
* Inefficient under packet loss

---

# 🔴 8. Selective Repeat ARQ

### 🔹 Implementation

* Sent multiple packets continuously
* Conceptual buffering assumed

### 🔍 Observations

* Only lost packet retransmitted (conceptually)
* Better efficiency compared to Go-Back-N

### ⚠️ Limitation

* Full selective ACK and buffering not supported in Packet Tracer

---

# 📊 9. Performance Comparison

| Protocol         | Frames Sent | Error Handling  | Retransmission | Efficiency |
| ---------------- | ----------- | --------------- | -------------- | ---------- |
| Stop-and-Wait    | 1           | Single frame    | 1              | Low        |
| Go-Back-N        | Multiple    | All after error | Many           | Medium     |
| Selective Repeat | Multiple    | Only lost frame | 1 (ideal)      | High       |

---

# 📊 10. Observations

* Stop-and-Wait is reliable but slow
* Go-Back-N improves utilization but wastes bandwidth under errors
* Selective Repeat provides best efficiency in error-prone networks
* Increasing error rate highlights advantages of Selective Repeat

---

# ⚠️ 11. Challenges Faced

* Limited protocol-level implementation in simulation
* Differentiating Go-Back-N and Selective Repeat visually
* Simulating realistic packet loss

---

# 🚀 12. Improvements

* Simulate higher traffic loads
* Introduce delay or jitter
* Analyze throughput quantitatively
* Implement advanced retransmission strategies

---

# 🧾 13. Conclusion

The simulation successfully demonstrated flow control and error control mechanisms. Stop-and-Wait showed simplicity but low efficiency, Go-Back-N improved performance but wasted bandwidth during errors, and Selective Repeat proved to be the most efficient protocol in handling packet loss.

---

# ▶️ 14. How to Run the Simulation

1. Open `.pkt` file in Cisco Packet Tracer
2. Switch to Simulation Mode
3. Enable ICMP filter
4. Use Add Simple PDU to send packets
5. Use Capture/Forward to observe
6. Delete packets to simulate errors

---

# 📁 15. Files Included

* `stop_and_wait.pkt`
* `go_back_n_arq.pkt`
* `selective_repeat_arq.pkt`
* `README.md`
* `output.txt`
* `test_cases.txt`

---

# 📌 Assumptions & Design Decisions

* Simple topology used to isolate protocol behavior
* ICMP packets used as frame representation
* Packet deletion used to simulate errors
* Selective Repeat analyzed conceptually due to tool limitations

---

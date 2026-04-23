# 🌐 Sliding Window Protocol with Piggybacking Simulation



# 📖 1. Objective

The objective of this assignment is to simulate the **Sliding Window Protocol with Piggybacking** to demonstrate efficient data transmission and error control between two nodes.

---

# 🧠 2. Concepts Covered

* Sliding Window Protocol
* Flow Control
* Error Control
* Piggybacking
* Sequence Numbers and Acknowledgments

---

# 🏗️ 3. Network Topology

The network consists of:

* 2 PCs (Sender and Receiver)
* 1 Switch

### 🔹 Logical Diagram

```
PC0 -------- SWITCH -------- PC1
(Sender)                  (Receiver)
```
![Uploading Screenshot_2026-04-23_10-19-02.png…]()

---

# 🔌 4. Network Configuration

## 📍 IP Addressing

| Device | IP Address  |
| ------ | ----------- |
| PC0    | 192.168.1.1 |
| PC1    | 192.168.1.2 |

---

## 🔗 Cabling

* Copper Straight-Through cables used
* Connected via switch

---

# 🔄 5. Sliding Window Protocol

The sliding window protocol allows the sender to transmit multiple frames before receiving acknowledgments. Each frame is assigned a sequence number, and the window moves forward as acknowledgments are received.

---

# 🔁 6. Piggybacking

Piggybacking improves efficiency by combining acknowledgments with outgoing data frames instead of sending them separately.

---

# ⚙️ 7. Simulation Procedure

1. Configured IP addresses for both PCs
2. Verified connectivity using ping
3. Switched to Simulation Mode
4. Sent multiple PDUs using Add Simple PDU
5. Observed packet flow and acknowledgments
6. Monitored sequence numbers and window movement

---

# 🔍 8. Observations

* Multiple packets were sent before acknowledgment
* Window moved forward after ACK reception
* Acknowledgments were combined with outgoing packets (piggybacking)
* Reduced overhead due to fewer ACK packets

---

# 📊 9. Analysis

## 🔹 Efficiency

* Sliding window improves throughput
* Piggybacking reduces network overhead

## 🔹 Reliability

* Lost packets can be retransmitted
* Sequence numbers ensure correct ordering

---

# 📈 10. Impact of Window Size

* Small window → lower throughput
* Large window → higher efficiency but risk of congestion

---

# ⚠️ 11. Challenges Faced

* Understanding visualization in Simulation Mode
* Identifying piggybacked acknowledgments
* Tracking sequence numbers

---

# 🚀 12. Improvements

* Simulate packet loss
* Test different window sizes
* Add delay/jitter conditions

---

# 🧾 13. Conclusion

The simulation successfully demonstrated the sliding window protocol with piggybacking. It improved data transmission efficiency by allowing multiple frames and combining acknowledgments with outgoing data.

---

# ▶️ 14. How to Run

1. Open `.pkt` file in Cisco Packet Tracer
2. Switch to Simulation Mode
3. Send PDUs between PC0 and PC1
4. Use Capture/Forward to observe packets

---

# 📁 15. Files Included

* `sliding_window_with_piggybacking.pkt`
* `README.md`
* `output.txt`
* `test_cases.txt`

---

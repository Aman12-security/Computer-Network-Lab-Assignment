# Experiment 6: Multiple Access Protocols Simulation
## Pure ALOHA, Slotted ALOHA, CSMA/CD, and CSMA/CA


## 1. Objective
To simulate and analyze the performance of multiple access protocols (Pure ALOHA, Slotted ALOHA, CSMA/CD, and CSMA/CA) in handling collisions and maximizing data transmission efficiency using Cisco Packet Tracer.

## 2. Network Topology Design

**For Pure ALOHA, Slotted ALOHA, and CSMA/CD:**
- Devices: 4 PCs (PC0, PC1, PC2, PC3) + 1 PT-Hub
- All PCs connected to the PT-Hub using straight-through cables
- IP Configuration (same subnet):
  - PC0: 192.168.1.1 / 255.255.255.0
  - PC1: 192.168.1.2 / 255.255.255.0
  - PC2: 192.168.1.3 / 255.255.255.0
  - PC3: 192.168.1.4 / 255.255.255.0

**For CSMA/CA:**
- Devices: 4 PCs + 1 Access Point-PT
- Wireless modules (WPC300N) added to each PC
- All PCs connected wirelessly to the Access Point-PT
- Same IP configuration as above

**Simulation Tool:** Cisco Packet Tracer – Simulation Mode  
**Traffic:** ICMP PDUs (Simple PDU) used to simulate data frames

## 3. Protocol Explanations & Implementation

### Pure ALOHA (`pure_aloha.pkt`)
- Stations transmit at any random time.
- High probability of collision if two or more stations transmit simultaneously.
- After collision, stations wait a random time and retransmit.
- Simulation: Sent packets randomly and quickly from different PCs. Observed frequent collisions.

### Slotted ALOHA (`slotted_aloha.pkt`)
- Time is divided into fixed slots.
- Stations can transmit only at the beginning of a slot.
- Reduces partial overlap collisions compared to Pure ALOHA.
- Simulation: Sent packets at regular intervals (simulating slots). Fewer collisions observed than Pure ALOHA.

### CSMA/CD (`csma_cd.pkt`)
- Carrier Sense Multiple Access with Collision Detection (used in wired Ethernet).
- Devices listen before transmitting. If collision detected during transmission, stop, send jam signal, and back-off.
- Simulation: Sent many packets very quickly from multiple PCs. Collisions were detected and handled with retransmissions after back-off.

### CSMA/CA (`csma_ca.pkt`)
- Carrier Sense Multiple Access with Collision Avoidance (used in Wi-Fi).
- Uses RTS/CTS handshake to avoid collisions before data transmission.
- Simulation: Wireless topology with Access Point-PT. Observed RTS → CTS → Data sequence with very few collisions.

## 4. Performance Comparison

| Protocol      | Medium    | Collision Handling                  | Collision Rate | Efficiency     | Best Suitable For      |
|---------------|-----------|-------------------------------------|----------------|----------------|------------------------|
| Pure ALOHA    | Wired     | Random retransmission after collision | Very High      | Lowest         | Very low traffic       |
| Slotted ALOHA | Wired     | Slot-based transmission             | High           | Low-Medium     | Moderate traffic       |
| CSMA/CD       | Wired     | Detect collision + Jam + Backoff    | Medium         | High           | Wired LAN (Ethernet)   |
| CSMA/CA       | Wireless  | RTS/CTS handshake (Avoidance)       | Very Low       | Highest        | Wireless Networks (Wi-Fi) |

**Key Findings:**
- Pure ALOHA suffers from the highest number of collisions and lowest efficiency.
- Slotted ALOHA improves performance by reducing partial overlaps.
- CSMA/CD is much more efficient than ALOHA protocols in wired networks due to collision detection.
- CSMA/CA performs best in wireless environments by avoiding collisions through RTS/CTS mechanism.
- As traffic load increases, CSMA protocols (especially CSMA/CA) handle collisions far better than ALOHA protocols.

## 5. Simulation Instructions
1. Open the respective `.pkt` file in Cisco Packet Tracer.
2. Switch to **Simulation** mode.
3. Go to **Edit Filters** → Enable only **ICMP**.
4. Use **Add Simple PDU** to generate traffic between PCs.
5. For error/collision simulation: Send packets rapidly or at specific timings.
6. Observe collisions and retransmissions using **Capture/Forward** button.
7. Take screenshots from Event List for documentation.

**Note:** Packet Tracer does not implement the exact internal algorithms of these protocols. We simulated their behavior by controlling transmission timing and observing collision patterns in Simulation Mode.

## 6. Files Included
- `pure_aloha.pkt`
- `slotted_aloha.pkt`
- `csma_cd.pkt`
- `csma_ca.pkt`
- `output.txt`
- `test_cases.txt`
- This `README.md`

## 7. Assumptions and Limitations
- PT-Hub was used for wired protocols to generate collisions.
- Wireless module (WPC300N) added to PCs for CSMA/CA.
- Manual control of PDU timing was used to simulate different traffic loads.
- Results are based on visual observation in Simulation Mode.

All simulations are repeatable using the steps mentioned above.

---


```txt
Output File - Multiple Access Protocols Simulation
=================================================

Summary of Observations:

1. Pure ALOHA:
   - Highest collision rate when packets sent randomly.
   - Many retransmissions observed.
   - Lowest efficiency.

2. Slotted ALOHA:
   - Fewer collisions than Pure ALOHA when transmissions were timed.
   - Still significant collisions under high load.
   - Better than Pure ALOHA but not efficient.

3. CSMA/CD:
   - Collisions detected during transmission.
   - Jam signal and back-off mechanism observed.
   - Good efficiency in wired shared medium.

4. CSMA/CA:
   - Very few collisions due to RTS/CTS handshake.
   - Highest efficiency in wireless environment.
   - Best performance among all four protocols.

Conclusion:
CSMA/CA > CSMA/CD > Slotted ALOHA > Pure ALOHA in terms of collision handling and efficiency.

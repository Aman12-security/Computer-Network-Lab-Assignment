# Assignment: Packet Switching vs Circuit Switching in Cisco Packet Tracer

**Student Name:** Aman Singhal  


## 1. Network Design
- Both simulations use identical topology: 2 LANs connected via Router0.
- Packet switching file demonstrates independent packet routing.
- Circuit switching file uses continuous ping (`-t`) to simulate dedicated circuit.

## 2. Device Configuration & Connectivity
- IPs and router config as shown in the steps above.
- All cables: Copper Straight-Through.

## 3. Data Transmission Simulation
- **Packet Switching**: Simulation mode + Simple PDU (individual packets).
- **Circuit Switching**: Realtime mode + `ping <IP> -t` (persistent connection).

## 4. Performance Analysis
[Insert the comparison table above + 2–3 screenshots]

## 5. Screenshots
<img width="1500" height="850" alt="Screenshot_2026-04-19_20-02-40" src="https://github.com/user-attachments/assets/fbc1b575-b0b7-43ee-a253-0ecaa1001bce" />
<img width="1500" height="850" alt="Screenshot_2026-04-19_20-09-04" src="https://github.com/user-attachments/assets/ed73c016-1ce0-4653-ae82-d0f2ac669380" />

- Topology of both files
- Simulation mode packet flow (packet_switching.pkt)
- Continuous ping output (circuit_switching.pkt)
- Ping statistics

## How to Run
1. Open `packet_switching.pkt` → switch to Simulation mode → send Simple PDUs.
2. Open `circuit_switching.pkt` → Realtime mode → run `ping 192.168.2.1 -t` on PC0.

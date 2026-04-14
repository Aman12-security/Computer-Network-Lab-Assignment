# Experiment Title: Network Load and Delay
## Aim
To investigate the effect of network load on delay and packet drops in a Local Area Network (LAN).

## Objective
- Generate multiple concurrent pings to simulate traffic load.
- Observe how delays and packet drops increase under high network load.
- Compare network performance under low vs high traffic conditions.

## Theory
- **ICMP (Internet Control Message Protocol)**: Used for sending diagnostic messages such as echo requests (ping).
- **Network Congestion**: Occurs when network traffic exceeds its capacity, causing delays and packet drops.
- **Packet Queueing**: As traffic increases, packets are queued in switches or routers, causing delays. If the queue exceeds capacity, packets are dropped.
  

### Description:
- **1 Switch**
- **6 PCs** with IP addresses:
  - PC1: 192.168.10.1
  - PC2: 192.168.10.2
  - PC3: 192.168.10.3
  - PC4: 192.168.10.4
  - PC5: 192.168.10.5
  - PC6: 192.168.10.6

## Step-by-step Procedure
1. **Baseline Test (Low Traffic)**: 
   - Ping from PC1 → PC6 and record ping success and delay times.
2. **High Traffic Test**: 
   - Simultaneously ping from PC1 → PC6, PC2 → PC5, and PC3 → PC4.
   - Observe event logs and packet behavior under load.
3. **Observation Summary**: 
   - Compare the results of the low traffic and high traffic tests. Focus on delay times and packet loss.

## Configuration Commands
- For PCs, assign static IPs:
  - PC1: `192.168.10.1/24`
  - PC2: `192.168.10.2/24`
  - PC3: `192.168.10.3/24`
  - PC4: `192.168.10.4/24`
  - PC5: `192.168.10.5/24`
  - PC6: `192.168.10.6/24`
  
  Example for PC1:
  - Command: `ip 192.168.10.1 255.255.255.0`

## Observations / Results
- **Low Traffic Test**: Ping success was 100%, with delays under 10ms.
- **High Traffic Test**: Observed increased delays and packet drops. Delays increased as network congestion built up.
- **Simulation Event Logs**: Significant delay and packet drops occurred during simultaneous pings.


## Conclusion
This experiment demonstrated the effect of network load on delay and packet loss. By generating multiple concurrent pings, we observed how congestion affects network performance, which highlights the importance of managing network traffic and employing Quality of Service (QoS) mechanisms.

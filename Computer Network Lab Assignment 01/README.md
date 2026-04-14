# Network Topologies Assignment - Aman Singhal

## Topologies Designed
1. Bus (Hub) - bus_topology.pkt  
2. Star (Switch) - star_topology.pkt  
3. Ring (4 Switches loop) - ring_topology.pkt  
4. Mesh (full switch mesh) - mesh_topology.pkt

## IP Addressing
PC0: 192.168.1.1  
PC1: 192.168.1.2 etc.

## Comparison Table
Topology | Advantages | Disadvantages | Efficiency (data flow)
---|---|---|---
Bus | Cheap, simple | Single failure kills all, collisions | Poor under load
Star | Easy to add devices, no collisions | Central switch failure | Very good
Ring | Orderly access | One break = total failure | Medium
Mesh | Multiple paths, fault tolerant | Many cables | Excellent

## Screenshots
### Bus
![Screenshot](Screenshot%201.png)
### Star
![Screenshot](Screenshot%202.png)
### Ring
![Screenshot](Screenshot%203.png)
### Mesh
![Screenshot](Screenshot%204.png)
## How to run
1. Open Cisco Packet Tracer  
2. Open any .pkt file  
3. Click PCs → Desktop → Command Prompt → ping others

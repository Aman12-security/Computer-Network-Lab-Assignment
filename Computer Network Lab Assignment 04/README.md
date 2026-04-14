# Experiment Title: Transmission Failure Demonstration
## Aim
To observe the effect of link failures on transmission and the recovery process after a link is re-established.

## Objective
- Demonstrate the impact of broken links on communication.
- Observe packet failure and recovery in a simulated environment.
- Understand the role of redundancy in maintaining reliable communication.

## Theory
- **Link Failure**: Occurs when a physical link between devices is lost, resulting in communication breakdown.
- **ICMP Failure**: When the link fails, ICMP packets cannot be delivered, and the ping command will fail.
- **Redundancy**: Redundant links or devices can help recover from link failures quickly.


### Description:
- **1 Switch**
- **2 PCs** with IP addresses:
  - PC1: 192.168.40.1
  - PC2: 192.168.40.2

## Step-by-step Procedure
1. **Normal Communication**:
   - Ping from PC1 → PC2 and verify successful communication.
2. **Force Error**:
   - Disconnect the cable between PC2 and the switch while pinging.
   - Observe packet drops and timeouts.
3. **Recovery**:
   - Reconnect the cable and verify that communication resumes.
   - Document the time it takes for the ping to recover.

## Configuration Commands
- For PCs, assign static IPs:
  - PC1: `192.168.40.1/24`
  - PC2: `192.168.40.2/24`
  
  Example for PC1:
  - Command: `ip 192.168.40.1 255.255.255.0`

## Observations / Results
- **Normal Communication**: Successful ping between PCs with no packet loss.
- **Link Failure**: After disconnecting the link, pings failed with a timeout.
- **Recovery**: After reconnecting the link, pings resumed, but there was a noticeable delay during recovery.


## Conclusion
The experiment demonstrated how link failures affect communication and the importance of recovery procedures. Redundant paths or links are essential for maintaining communication in case of link failures, and proper troubleshooting methods can restore service efficiently.

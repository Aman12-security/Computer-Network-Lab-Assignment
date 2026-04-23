# 🌐 DNS and DDNS Simulation in Cisco Packet Tracer


# 📖 1. Objective

The objective of this assignment is to simulate the working of the **Domain Name System (DNS)** and **Dynamic Domain Name System (DDNS)**. The simulation demonstrates how domain names are resolved to IP addresses and how DNS records can be updated dynamically in a network environment.

---

# 🧠 2. Concepts Covered

* DNS (Domain Name Resolution)
* DDNS (Dynamic DNS Updates)
* Client-Server Communication
* Name-to-IP Mapping
* Network Configuration and Testing

---

# 🏗️ 3. Network Topology

The network consists of:

* 1 Server (DNS + DDNS)
* 2 Client PCs
* 1 Switch

### 🔹 Logical Diagram

```id="topo1"
PC0        PC1
  \        /
   \      /
    SWITCH
       |
     SERVER
```
<img width="1374" height="445" alt="Screenshot_2026-04-23_00-10-06" src="https://github.com/user-attachments/assets/2a00ee99-ead7-4f68-a0b1-db8160404dd9" />

---

# 🔌 4. Network Configuration

## 📍 IP Addressing

| Device | IP Address  | Subnet Mask   | DNS Server  |
| ------ | ----------- | ------------- | ----------- |
| Server | 192.168.1.1 | 255.255.255.0 | —           |
| PC0    | 192.168.1.2 | 255.255.255.0 | 192.168.1.1 |
| PC1    | 192.168.1.3 | 255.255.255.0 | 192.168.1.1 |

---

## 🔗 Cabling

* All devices are connected using **Copper Straight-Through cables**
* Communication occurs through a switch

---

# 🔧 5. DNS Configuration

* DNS service was enabled on the server
* The following DNS records were added:

| Domain Name | IP Address  |
| ----------- | ----------- |
| example.com | 192.168.1.1 |
| test.com    | 192.168.1.1 |

---

# 💻 6. DNS Query Testing

## 🔹 Using Web Browser

* Accessed `example.com` from PC0
  ✔ Result: Successfully resolved to server IP and loaded webpage

---

## 🔹 Using Command Prompt

Command used:

```
nslookup test.com
```

✔ Result: Returned correct IP address (192.168.1.1)

---

# 🔄 7. DDNS Simulation (Dynamic Updates)

Since real dynamic updates are not fully supported in Cisco Packet Tracer, DDNS was simulated manually.

---

## ➕ Adding New Record

| Domain      | IP          |
| ----------- | ----------- |
| test.com    | 192.168.1.4 |

---
<img width="1502" height="263" alt="Screenshot_2026-04-23_00-09-43" src="https://github.com/user-attachments/assets/06e80d5f-f610-4278-bcb2-bd13b053c967" />

## 🔁 Updating Existing Record

| Domain      | Updated IP  |
| ----------- | ----------- |
| test.com    | 192.168.1.5 |

---

# ✅ 8. Verification of Updates

## 🔹 Command Line Test

```
nslookup test.com
```
<img width="731" height="319" alt="Screenshot_2026-04-23_00-04-56" src="https://github.com/user-attachments/assets/224b9c7b-e510-4f6d-83b1-087b8a0d1b45" />

✔ Result: Updated IP address reflected successfully

---

## 🔹 Browser Test

* Accessed `example.com`
  ✔ Result: Successfully resolved and connected
<img width="1707" height="706" alt="Screenshot_2026-04-22_23-56-04" src="https://github.com/user-attachments/assets/ef1ccdf4-4e44-4077-8ab1-3c826f021a38" />

---

# 🔍 9. Analysis

## 🔹 DNS Behaviour

* Converts human-readable domain names into IP addresses
* Enables easier network communication

---

## 🔹 DDNS Behaviour

* Allows updating DNS records dynamically
* Useful in environments with frequently changing IP addresses

---

# 📊 10. Observations

* DNS queries were resolved successfully
* Updated DNS records were reflected immediately
* Domain-based access worked correctly via browser
* System demonstrated real-world DNS behavior

---

# ⚠️ 11. Challenges Faced

* Incorrect DNS mapping initially caused connection errors
* Ensuring DNS service was enabled on the server
* Understanding difference between DNS resolution and HTTP access

---

# 🚀 12. Improvements / Extensions

* Integrate DNS with HTTP server for realistic browsing
* Add multiple servers and domains
* Simulate larger network environments
* Explore DNS caching behavior

---

# 🧾 13. Conclusion

The simulation successfully demonstrated the working of DNS and DDNS. DNS resolved domain names efficiently, while DDNS allowed updates to be reflected dynamically. This provides a clear understanding of how modern networks manage domain name resolution.

---

# ▶️ 14. How to Run the Simulation

1. Open the `.pkt` file in Cisco Packet Tracer
2. Verify all connections are active
3. Open PC → Command Prompt → Test using `nslookup`
4. Open Web Browser → Enter domain name
5. Observe resolution and connectivity

---

# 📁 15. Files Included

* `dns_ddns.pkt`
* `README.md`
* `output.txt`
* `test_cases.txt`

---

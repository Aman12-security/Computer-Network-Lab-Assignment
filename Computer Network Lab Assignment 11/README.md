# 🌐 Web Server Simulation: HTTP and WWW Basics



# 📖 1. Objective

The objective of this assignment is to simulate the working of the **Hypertext Transfer Protocol (HTTP)** and understand how the **World Wide Web (WWW)** functions using a client-server model. The simulation demonstrates how web clients request resources and how servers respond with web content.

---

# 🧠 2. Concepts Covered

* HTTP Protocol (Request–Response Model)
* Client-Server Architecture
* Web Browsing and Content Retrieval
* TCP/IP Communication Basics
* Packet-level Visualization using Simulation Mode

---

# 🏗️ 3. Network Topology

The network consists of:

* 1 Web Server
* 2 Client PCs
* 1 Switch

### 🔹 Logical Diagram

```
PC0        PC1
  \        /
   \      /
    SWITCH
       |
     SERVER
```

---

# 🔌 4. Network Configuration

## 📍 IP Addressing

| Device | IP Address  | Subnet Mask   | Default Gateway |
| ------ | ----------- | ------------- | --------------- |
| Server | 192.168.1.1 | 255.255.255.0 | —               |
| PC0    | 192.168.1.2 | 255.255.255.0 | 192.168.1.1     |
| PC1    | 192.168.1.3 | 255.255.255.0 | 192.168.1.1     |

---

## 🔗 Cabling

* All devices are connected using **Copper Straight-Through cables**
* Connections are made via FastEthernet ports through a switch

---

# 🌐 5. Web Server Configuration

* HTTP service was enabled on the server
* A custom HTML page (`index.html`) was created

## 📄 index.html

```html
<html>
<head><title>My Web Server</title></head>
<body>
<h1>Welcome to Cisco Packet Tracer Web Server!</h1>
<p>This is my HTTP simulation assignment.</p>
</body>
</html>
```

---

# 💻 6. Client Configuration and Testing

## 🔹 Step 1: Connectivity Test

Command used:

```
ping 192.168.1.1
```

✔ Result: Successful communication with the server

---

## 🔹 Step 2: Web Access

* Opened Web Browser on PC0 and PC1
* Entered:

```
http://192.168.1.1
```

✔ Result: Web page successfully loaded

---

# 🔍 7. HTTP Simulation (Simulation Mode)

Using Simulation Mode:

### Observed Steps:

1. Client sends **HTTP GET request**
2. Server processes the request
3. Server sends **HTTP Response**
4. Client renders the webpage

---

# 📡 8. Protocol Analysis

## 🔹 HTTP Characteristics

* Stateless protocol
* Works on **Request–Response model**
* Uses **TCP (Port 80)** for communication

---

## 🔄 Communication Flow

1. Client initiates request (GET)
2. Server responds with HTML content
3. Browser displays webpage

---

# 📊 9. Observations

* Successful HTTP communication between client and server
* Proper packet flow observed in Simulation Mode
* Web page retrieval completed without errors
* Demonstrated real-world web browsing behavior

---

# Screenshots
<img width="1791" height="860" alt="Screenshot_2026-04-22_22-14-27" src="https://github.com/user-attachments/assets/57e8d243-31de-4c06-b376-f39eebbb0558" />

<img width="1791" height="860" alt="Screenshot_2026-04-22_22-14-40" src="https://github.com/user-attachments/assets/1b1d91c5-6d7a-4974-83d3-a666068bd504" />

<img width="831" height="515" alt="Screenshot_2026-04-22_22-14-58" src="https://github.com/user-attachments/assets/ee364003-e94c-42eb-a21e-dc1e308b8d7b" />

<img width="1395" height="655" alt="Screenshot_2026-04-22_22-15-09" src="https://github.com/user-attachments/assets/a7a5f4f8-ffc0-4770-b17d-80c7377df8a4" />


# ⚠️ 10. Challenges Faced

* Ensuring correct IP configuration
* Verifying HTTP service was enabled on server
* Understanding Simulation Mode packet flow

---

# 🚀 11. Improvements / Extensions

* Add multiple web pages (e.g., about.html)
* Simulate multiple clients accessing server simultaneously
* Explore HTTP POST requests
* Implement DNS for domain-based access

---

# 🧾 12. Conclusion

This simulation successfully demonstrated how HTTP enables communication between web clients and servers. It illustrated the request-response mechanism and provided practical insights into how web content is delivered over a network.

---

# ▶️ 13. How to Run the Simulation

1. Open the `.pkt` file in Cisco Packet Tracer
2. Verify all devices are connected
3. Open PC → Desktop → Command Prompt → Test using `ping`
4. Open Web Browser → Enter server IP
5. Switch to Simulation Mode to observe HTTP packets

---

# 📁 14. Files Included

* `web_server_simulation.pkt`
* `index.html`
* `README.md`
* `output.txt`
* `test_cases.txt`

---

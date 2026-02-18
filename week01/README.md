# Week 01 — Ping, Traceroute, and Wireshark (ICMP)

## Goal
The goal of this experiment is to observe how packets travel across the Internet using `ping`, `tracert`, and Wireshark, and to understand the roles of ICMP messages and TTL in network communication.

---

## Setup
- Operating System: Windows  
- Tools Used: PowerShell (`ping`, `tracert`), Wireshark  
- Test Targets:
  - google.com  
  - www.bilibili.com  

---

## 1) Ping Tests

### Command Used
ping -n 10 google.com
ping -n 10 www.bilibili.com

### Result Screenshot
![Ping result](screenshots/7c092c5999ca0ea42ecea515a05aa020.png)

### Observations
- The RTT values are different for different destinations.
- The server that is farther away shows higher delay.
- There is no packet loss in this test, which means the connection is stable.


---

## 2) Traceroute Tests

### Command Used
tracert google.com
tracert www.bilibili.com

### Screenshot
![Traceroute Results](9088cade9b8f62c7c79e8465c6bc3bbe.png)

### Observations
- Multiple hops can be seen between the local machine and the destination.
- Some hops may not respond and show `* * *`, probably because routers block ICMP replies.
- The distant website generally has more hops than the closer one.

---

## 3) Wireshark ICMP Capture

### Filter Used
icmp

### Procedure
Wireshark was started on the active Wi-Fi interface.  
While capturing packets, the following command was executed:

ping -n 4 8.8.8.8

### Screenshot
![ICMP Capture](screenshots/4f118bf1018954d88231adce4ccb9ed1.png)

### Observations
- ICMP echo request and reply packets are captured successfully.
- The source and destination addresses match the ping command.
- The TTL value decreases across routers, which prevents packets from looping forever.
- Packet details in Wireshark provide more information than command-line tools.

---

## Conclusion
This lab shows how ping and traceroute work in real networks and how ICMP is used for connectivity testing.  
Using Wireshark makes it possible to directly see packet headers and protocol behavior, which helps understand how data actually travels on the Internet.


---

## Files Included


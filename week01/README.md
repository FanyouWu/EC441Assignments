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
- The round-trip time (RTT) to different destinations is not the same.
- Distant or cross-border servers usually show **higher RTT**.
- Packet loss is typically **0%** under stable network conditions.

---

## 2) Traceroute Tests

### Command Used

# Project 2: Suspicious Traffic Detection using Wireshark

## Objective
To analyze network traffic and identify suspicious patterns such as port scanning, repeated HTTP requests, and ICMP activity.

---

## Tools
- Wireshark
- Nmap
- curl
- ping

---

## Activities

### 1. Port Scanning
Command:
nmap 127.0.0.1

Filter:
tcp.flags.syn == 1 && tcp.flags.ack == 0

Observation:
Multiple SYN packets were sent to different ports in a short time. Most responses were RST, indicating closed ports.

---

### 2. Repeated HTTP Requests
Command:
for i in {1..20}; do curl http://example.com; done

Filter:
http

Observation:
Multiple HTTP GET requests were generated rapidly to the same destination.

---

### 3. ICMP Activity
Command:
ping -4 -c 50 -i 0.2 8.8.8.8

Filter:
icmp

Observation:
Repeated ICMP echo requests and replies were observed with short intervals.

---

## Screenshots

- syn_scan.png
- repeated_http_requests.png
- icmp_flood.png

---

## Conclusion
This project demonstrates how common suspicious patterns such as scanning, automation, and repeated network activity can be identified using Wireshark.

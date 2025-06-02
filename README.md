 Network Traffic Analysis Report
This repository contains the analysis of a captured network traffic log, focusing on key protocols such as ARP, DNS, and ICMP. The report highlights host communication patterns, connectivity status, and protocol-specific behaviors based on the traffic observed.

 Report Summary
1. Overview of Network Activities
The analyzed network traffic includes:

ARP (Address Resolution Protocol) – Resolving IP to MAC addresses.

DNS (Domain Name System) – Resolving domain names to IPs.

ICMP (Internet Control Message Protocol) – Used for diagnostics (ping).

ICMPv6 – IPv6 router discovery activity.

2. Host Identification
IP Address	MAC Address	Notes
192.168.197.132	PCSSystemtec_04:42:0f	Active, responded to ARP
192.168.197.204	f2:d8:cc:a3:8a:85	Active, performed ARP and DNS resolutions
192.168.197.223	Unknown	No ARP replies; possibly offline or unreachable
172.67.179.238	N/A	Public IP (resolved from DNS query)
fe80::1966:2077:...	N/A	IPv6 local-link address
ff02::2	N/A	IPv6 multicast (router solicitation)

📡 3. Protocol-Specific Observations
🔁 3.1 ARP (Address Resolution Protocol)
Normal bidirectional ARP between 192.168.197.132 and 192.168.197.204.

Repeated unanswered ARP requests for 192.168.197.223.

 3.2 DNS (Domain Name System)
Queries from 192.168.197.132 for:

redteamacademy.com (A and AAAA records)

DNS responses from 192.168.197.204 returned:

IPv4: 172.67.179.238, 104.21.31.200

IPv6: 2606:4700:3034::6815:1fc8, 2606:4700:3036::ac43:b3ee

Reverse DNS (PTR) for 172.67.179.238 returned "No such name".

 3.3 ICMP (Ping)
Successful ping sequence from 192.168.197.132 to 172.67.179.238.

Every echo request received a valid reply.

TTL = 57 in replies, indicating multi-hop routing.

 3.4 ICMPv6
Router Solicitation observed from fe80::... to ff02::2.

Indicates presence of IPv6 and router discovery behavior.

 4. Key Observations
 Normal ARP, DNS, and ICMP behaviors observed.

 Domain name resolution and IPv6 records retrieved successfully.

 Full connectivity established with external host (redteamacademy.com).

 ARP requests for 192.168.197.223 unanswered — potential offline device.

 No reverse DNS entry for 172.67.179.238 — common for CDN or cloud IPs.

 IPv6 traffic present — network is dual-stack capable.


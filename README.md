# FTP-DoS-PCAP-Investigation
PCAP-based investigation of an FTP Denial-of-Service attack, analyzing traffic spikes, attacker behavior, and service impact.

## Overview
This project presents a **network forensics investigation** of a suspected **Denial-of-Service (DoS) attack** targeting an FTP server.  
The analysis is based on captured network traffic (PCAP) and focuses on identifying abnormal FTP behavior, attacker activity, and the overall impact on the service.

---

## Incident Summary
A DoS attack was reported against an FTP server after noticeable spikes in FTP traffic.  
The server eventually became unavailable, prompting a forensic investigation using packet capture analysis.

---

## Known Information
- **FTP Server IP:** `192.168.56.1`
- **Attacking Host IP:** `192.168.56.101`
- **Protocol Analyzed:** FTP (TCP/21)
- **Data Source:** PCAP file

---

## Key Investigation Questions
- What caused the spike in FTP traffic?
- What events occurred immediately before the server went offline?
- Did the attacker successfully authenticate?
- Were any files accessed, modified, or exfiltrated?
- What type of attack was performed on the FTP service?

---

## Investigation Methodology
- Analyzed PCAP traffic using **Wireshark**
- Applied protocol and port filters:
  - `ftp`
  - `ftp-data`
  - `tcp.port == 21`
- Reviewed:
  - FTP command frequency
  - Authentication attempts
  - Session behavior
  - Traffic volume and spikes

---

## Findings
- Abnormal spike in FTP traffic originating from the attacking host
- Repeated FTP commands indicating **flooding behavior**
- No confirmed successful authentication attempts *(based on current analysis)*
- No evidence of file transfer or data exfiltration detected

---

## Impact Assessment
- FTP service became unavailable due to excessive traffic
- Server resources were likely exhausted
- No confirmed data breach was identified

---

## Repository Structure

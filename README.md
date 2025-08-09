# elevate-task1
Port scanning task using Nmap - local network reconnaissance

# Task 1: Local Network Port Scan

## Objective
The objective of this task is to scan the local network to discover open ports on devices and understand network exposure and potential security risks.

## Tools Used
- Nmap (TCP SYN scan)
- (Optional) Wireshark (not used in this task)

## Steps Performed
1. Installed Nmap from the official website.
2. Identified the local IP range as `192.168.0.0/24`.
3. Ran the TCP SYN scan with the command:
4. Collected and saved the scan results in `scan_results.txt`.
5. Noted down IP addresses and open ports found.
6. Researched common services running on those ports and documented potential security risks.
7. (Optional) Wireshark analysis was skipped.

## Findings Summary
- Four active devices found on the network.
- Router at 192.168.0.1 had ports 53 (DNS), 80 (HTTP), 443 (HTTPS - filtered), 49152 (UPnP), and port 1 (tcpmux filtered) open.
- A Windows PC at 192.168.0.141 had ports 135 (MSRPC), 139 (NetBIOS-SSN), 445 (SMB), and 7070 (RealServer) open.
- Other hosts had no open TCP ports detected.

## Potential Security Risks
- Open SMB ports (139, 445) on the Windows PC can be exploited by ransomware and malware.
- HTTP port on the router may expose the device management interface if not properly secured.
- UPnP port on the router can allow unauthorized network access if misconfigured.
- MSRPC and NetBIOS ports on Windows machine are common targets for remote exploits.

## Files Included
- `scan_results.txt`: Raw output from the Nmap scan.
- `open_ports_research.txt`: Research notes on common services and security risks.

---

## Interview Questions (Answered)

1. What is an open port?  
An open port is a network port that is accepting incoming connections, indicating a service is available on that port.

2. How does Nmap perform a TCP SYN scan?  
Nmap sends SYN packets and listens for SYN-ACK responses to identify open ports without completing the TCP handshake.

3. What risks are associated with open ports?  
Open ports can expose vulnerable services to attackers, enabling unauthorized access or exploitation.

4. Explain the difference between TCP and UDP scanning.  
TCP scanning relies on handshake responses; UDP scanning sends packets without handshakes and relies on error messages, making it slower and less reliable.

5. How can open ports be secured?  
By closing unnecessary ports, patching services, using firewalls, and enforcing strong authentication.

6. What is a firewall's role regarding ports?  
It filters network traffic, allowing or blocking access to ports based on security rules.

7. What is a port scan and why do attackers perform it?  
A port scan is a reconnaissance method to find open ports and potential attack vectors.

8. How does Wireshark complement port scanning?  
Wireshark captures and analyzes network packets, helping understand the traffic and detect anomalies during scans.


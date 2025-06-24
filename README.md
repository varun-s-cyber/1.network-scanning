# Network Scan for Open Ports 

## Overview

This repository contains the submission for "Task 1: Scan Your Local Network for Open Ports." The objective of this task was to learn how to discover open ports on devices within a local network to understand network exposure.

## Objective

To gain proficiency in identifying open ports on network devices, which is crucial for understanding potential network vulnerabilities and overall network security posture.

## Tools Used

* **Nmap (Network Mapper):** A free and open-source utility for network discovery and security auditing.
* **Wireshark:** A free and open-source packet analyzer used for network troubleshooting, analysis, software and communications protocol development, and education.

## Steps Performed

1.  **Nmap Installation:** Confirmed Nmap was installed and accessible on the Kali Linux environment.
2.  **Local IP Range Identification:** Identified the local IP range for scanning (e.g., `192.168.75.0/24`).
3.  **TCP SYN Scan with Nmap:** Executed a TCP SYN scan across the identified local IP range using Nmap.
    * Command used: `nmap -sS 192.168.75.0/24`
    * An example of the live scan output is provided in `Screenshot 2025-06-23 223538.jpg`.
4.  **IP Addresses and Open Ports Noted:** Documented the IP addresses and the open ports found on various hosts within the network.
    * The scan results were saved to a text file. An example of the saved output is available in `Screenshot 2025-06-23 224040.jpg`.
    * **Key Findings from Nmap Scan:**
        * **192.168.75.1:**
            * Open Ports: 135/tcp (msrpc), 139/tcp (netbios-ssn), 445/tcp (microsoft-ds), 902/tcp (iss-realsecure), 912/tcp (apex-mesh)
        * **192.168.75.2:**
            * Open Port: 53/tcp (domain - DNS)
        * **192.168.75.131:**
            * Open Port: 5357/tcp (wsdapi)
5.  **Optional Packet Capture Analysis with Wireshark:** Performed packet capture and analysis using Wireshark to observe network traffic, particularly focusing on protocols running over specific ports.
    * An example of a Wireshark capture showing HTTP traffic (on port 80) is provided in `Screenshot 2025-06-24 094335.png`. While port 80 wasn't open on the hosts identified by Nmap in this specific scan output, this screenshot demonstrates the capability to analyze service-specific traffic if found.
6.  **Research Common Services:** Researched the common services running on the identified open ports (e.g., `msrpc`, `netbios-ssn`, `microsoft-ds` for Windows file sharing/RPC; `domain` for DNS; `wsdapi` for Web Services for Devices).
7.  **Potential Security Risks Identification:** Identified potential security risks associated with the open ports, such as:
    * **SMB/NetBIOS (139, 445):** Vulnerabilities like EternalBlue, unauthenticated access to shares, or brute-force attacks.
    * **DNS (53):** DNS spoofing, cache poisoning, or denial-of-service attacks if not properly secured.
    * **RPC (135):** Various vulnerabilities depending on the specific RPC services exposed.
    * **Less common services (902, 912, 5357):** These would require further investigation to determine specific vulnerabilities, but any open port presents an attack surface.
8.  **Scan Results Saved:** The Nmap scan results were saved as a text file (`result.txt`).

## Outcome

This task successfully demonstrated basic network reconnaissance skills. By performing port scans and analyzing the results, a fundamental understanding of network service exposure was achieved. This knowledge is crucial for identifying potential attack vectors and improving network security.

## Screenshots

* `Screenshot 2025-06-23 223538.jpg`: Nmap scan in progress.
* `Screenshot 2025-06-23 224040.jpg`: Nmap scan results saved to `result.txt`.
* `Screenshot 2025-06-24 094335.png`: Wireshark packet capture analysis.

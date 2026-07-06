# Network Reconnaissance Project

Performed network reconnaissance against an authorized TryHackMe lab target using Nmap.

## Project Overview

This project demonstrates a complete network reconnaissance process against the TryHackMe Nmap room lab target.

The assessment included host discovery, full TCP port scanning, service and version enumeration, manual banner grabbing, OS fingerprinting, scan type comparison, packet fragmentation, and slow timing analysis.

## Tools Used

- Nmap
- curl
- Kali Linux
- OpenVPN

## Lab Environment

TryHackMe - Nmap: The Basics

## Authorization

All network scanning activities were performed only against an authorized TryHackMe lab target.

No unauthorized public or third-party systems were scanned.

## Key Findings

- Seven open TCP ports were identified.
- SSH, Samba, and HTTP services were discovered.
- Manual HTTP banner grabbing identified nginx 1.28.2 on port 7777.
- Nmap OS fingerprinting did not return an exact OS match.
- The fragmentation scan reported the tested ports as filtered.
- The T2 timing scan was slower but identified the same open ports.

## Repository Structure

scanning-project/
├── README.md
├── scan-commands.md
├── raw-output/
│   ├── host-discovery.txt
│   ├── full-port-scan.txt
│   ├── service-version.txt
│   ├── http-banner.txt
│   ├── os-detection.txt
│   ├── syn-scan.txt
│   ├── connect-scan.txt
│   ├── fragment-scan.txt
│   └── slow-scan.txt
└── report.md

## Resume Line

Performed network reconnaissance against a lab environment using Nmap, including host discovery, service/version enumeration, OS fingerprinting, and evasion techniques; documented findings in a professional reconnaissance report.

## Task-wise Documentation

Detailed process documentation for each network scanning task is available in the `documentation/` folder.

Each task includes:
- Objective
- Command Used
- Command Explanation
- Procedure
- Output Summary
- Observation
- Conclusion
- Evidence Reference

### Documented Tasks

1. Host Discovery
2. Full TCP Port Scan
3. Service and Version Detection
4. Manual HTTP Banner Grabbing
5. Operating System Detection
6. TCP SYN Scan
7. TCP Connect Scan
8. Packet Fragmentation Scan
9. Slow Timing Scan

[View Task-wise Scanning Documentation](documentation/README.md)

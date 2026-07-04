# Network Reconnaissance Report

## 1. Scope

A network reconnaissance assessment was conducted against the authorized TryHackMe Nmap room lab target.

Target IP: 10.48.84.93

Assessment Date: 04 July 2026

All network scanning activities were performed only against the authorized TryHackMe lab environment.

## 2. Methodology

The assessment began with host discovery to verify whether the target system was active.

A full TCP port scan was performed across all 65,535 TCP ports to identify exposed services.

Service and version detection was performed against the identified open ports using Nmap.

Manual HTTP banner grabbing was performed using curl to verify the web server software and version.

Nmap OS fingerprinting was used to attempt identification of the target operating system.

SYN and TCP Connect scans were performed against the same open ports and timed for comparison.

Packet fragmentation and a slower T2 timing template were tested to observe changes in scan results and scan duration.

## 3. Findings

| Host | Port | Service | Version | Notes |
|------|------|---------|---------|-------|
| 10.48.84.93 | 22 | SSH | OpenSSH 9.6p1 Ubuntu 3ubuntu13.16 | Remote access service |
| 10.48.84.93 | 53 | tcpwrapped | Not identified | Service connection wrapped |
| 10.48.84.93 | 139 | NetBIOS-SSN | Samba smbd 4 | Samba service |
| 10.48.84.93 | 445 | NetBIOS-SSN | Samba smbd 4 | Samba service |
| 10.48.84.93 | 7777 | HTTP | nginx 1.28.0 / banner 1.28.2 | Version difference observed |
| 10.48.84.93 | 7778 | HTTP | nginx 1.29.5 | HTTP service |
| 10.48.84.93 | 8443 | SSL/HTTPS-alt | Unrecognized service | Nmap returned service fingerprint |

## 4. Manual Banner Verification

Manual HTTP banner grabbing was performed against TCP port 7777 using curl.

Nmap service detection identified nginx 1.28.0.

The HTTP response banner returned:

Server: nginx/1.28.2

The manually observed banner did not exactly match the Nmap version detection result. This demonstrates why manual service verification is useful during network reconnaissance.

## 5. OS Fingerprinting

Nmap OS detection did not identify an exact operating system match.

The scan returned:

No exact OS matches for host.

Therefore, an OS fingerprint confidence percentage was not available.

However, Nmap service information indicated Linux as the likely operating system.

The target was located three network hops away.

## 6. SYN and TCP Connect Scan Comparison

The SYN scan completed in 0.80 seconds of real time.

The TCP Connect scan completed in 0.77 seconds of real time.

In this lab, the TCP Connect scan was slightly faster, although the difference was minimal.

For a stealth-focused authorized engagement, I would generally choose a SYN scan because it does not complete the full TCP three-way handshake for open ports and is typically less intrusive than a full TCP Connect scan.

## 7. Firewall and IDS Evasion Observations

### Packet Fragmentation

A packet fragmentation scan was performed using the Nmap -f option.

The standard scan identified seven open TCP ports.

The fragmentation scan reported all seven tested ports as filtered.

The fragmentation scan completed in 2.28 seconds.

This indicates that fragmented scan probes were handled differently by the target or network path.

### Slow Timing Scan

A slower T2 timing scan was performed against the same seven ports.

The T2 scan identified the same seven open TCP ports as the standard scan.

The T2 scan completed in 3.96 seconds of real time.

The slower timing template increased scan duration without changing the discovered open-port results.

### Decoy Scanning

Decoy scanning is an Nmap technique that mixes scan traffic associated with the real scanning host with traffic attributed to decoy addresses.

This can make source attribution more difficult in some network observations.

Decoy scanning should only be used during an explicitly authorized security assessment when permitted by the rules of engagement.

### Proxy Chaining

Proxy chaining routes supported network traffic through one or more proxy servers before reaching a destination.

During an authorized security assessment, approved proxy infrastructure may be used when the engagement requires traffic routing or source separation.

The compatibility of proxy chaining depends on the scanning technique and network protocol being used.

## 8. Risk Observations

Multiple network services were exposed on the target system, increasing the available network attack surface.

Samba services were accessible through TCP ports 139 and 445.

HTTP services were exposed on non-standard TCP ports 7777 and 7778.

The HTTP server on port 7777 exposed software version information through the Server response header.

A difference was observed between the Nmap service version result and the manually collected HTTP banner.

## 9. Recommendations

1. Review all exposed network services and disable services that are not operationally required.

2. Keep SSH, Samba, nginx, and other network-facing software updated and regularly review available security patches.

3. Reduce unnecessary software version disclosure in HTTP response headers and configure firewall and network monitoring controls around required services.

## 10. Conclusion

The network reconnaissance assessment identified seven open TCP ports on the authorized TryHackMe lab target.

Service enumeration identified SSH, Samba, and HTTP services.

Manual banner grabbing demonstrated a difference between automated version detection and the observed HTTP server banner.

OS fingerprinting did not return an exact operating system match.

The fragmentation scan produced different port states, while the T2 timing scan increased scan duration without changing the identified open ports.

The assessment demonstrates the importance of combining automated scanning with manual service verification during network reconnaissance.


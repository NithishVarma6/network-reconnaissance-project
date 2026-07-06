# Task 3: Service and Version Detection

## Objective
Identify the services and software versions running on the discovered open TCP ports.

## Command Used
```bash
nmap -sV -p 22,53,139,445,7777,7778,8443 -oN raw-output/service-version.txt 10.48.84.93
```

## Command Explanation
`-sV` enables service and version detection. `-p` limits the scan to the seven previously discovered open ports.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Used the open-port list from the full scan, executed version detection only against those ports, and reviewed the service fingerprints.

## Output Summary
Nmap identified OpenSSH 9.6p1 Ubuntu on port 22, Samba smbd 4 on ports 139 and 445, nginx 1.28.2 on port 7777, nginx 1.29.5 on port 7778, and a DCV-related SSL/HTTPS service on port 8443. Port 53 was reported as tcpwrapped.

## Observation
Version enumeration provided more detailed information than the initial port scan and indicated a Linux-based environment.

## Conclusion
Service and version detection was completed successfully, providing service fingerprints for targeted analysis.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

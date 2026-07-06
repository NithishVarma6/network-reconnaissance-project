# Task 7: TCP Connect Scan

## Objective
Perform a full TCP Connect scan against the known ports and compare the result with the SYN scan.

## Command Used
```bash
nmap -sT -p 22,53,139,445,7777,7778,8443 -oN raw-output/connect-scan.txt 10.48.84.93
```

## Command Explanation
`-sT` uses the operating system's TCP connect mechanism and completes the TCP connection when a port is reachable.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Executed the TCP Connect scan against the same seven ports used in the SYN scan and reviewed the result and scan duration.

## Output Summary
Ports 22, 53, 139, 445, 7777, 7778, and 8443 were all reported open. The scan completed in approximately 0.73 seconds.

## Observation
The Connect scan identified the same port states as the SYN scan in this lab environment.

## Conclusion
The TCP Connect scan successfully confirmed all seven open ports. In this test, SYN and Connect scans produced the same open-port results.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

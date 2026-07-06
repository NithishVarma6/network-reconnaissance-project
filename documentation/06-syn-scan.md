# Task 6: TCP SYN Scan

## Objective
Perform a TCP SYN scan against the known open ports and record the scan behavior and result.

## Command Used
```bash
nmap -sS -p 22,53,139,445,7777,7778,8443 -oN raw-output/syn-scan.txt 10.48.84.93
```

## Command Explanation
`-sS` performs a TCP SYN scan. It sends a SYN packet and evaluates the response without completing a normal full TCP connection for open ports.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Executed the SYN scan against the seven discovered ports and compared the reported states with the earlier full-port scan.

## Output Summary
All seven tested ports were reported open. The scan completed in approximately 0.75 seconds.

## Observation
The SYN scan quickly confirmed the same open ports discovered earlier.

## Conclusion
The TCP SYN scan successfully verified all seven open ports and provided a baseline for comparison with TCP Connect scanning.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

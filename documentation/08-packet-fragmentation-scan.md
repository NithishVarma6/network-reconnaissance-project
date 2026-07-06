# Task 8: Packet Fragmentation Scan

## Objective
Observe how the target or network path responds when Nmap uses fragmented IP packets during scanning.

## Command Used
```bash
nmap -f -p 22,53,139,445,7777,7778,8443 -oN raw-output/fragment-scan.txt 10.48.84.93
```

## Command Explanation
`-f` requests packet fragmentation for applicable scan traffic. The scan was performed only in the authorized lab environment.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Executed the fragmentation scan against the seven known ports and compared the reported states with the normal scan results.

## Output Summary
All seven tested ports were reported as filtered. The scan completed in approximately 2.28 seconds.

## Observation
The result differed from the normal scans, which reported the ports as open. Fragmented probe traffic did not produce enough responses for Nmap to confirm the ports as open.

## Conclusion
The fragmentation test demonstrated that changing packet structure can affect scan visibility and port-state interpretation.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

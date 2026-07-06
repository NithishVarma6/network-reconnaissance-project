# Task 9: Slow Timing Scan

## Objective
Perform a slower Nmap timing scan and compare its results and duration with faster scan executions.

## Command Used
```bash
nmap -T2 -p 22,53,139,445,7777,7778,8443 -oN raw-output/slow-scan.txt 10.48.84.93
```

## Command Explanation
`-T2` selects Nmap's Polite timing template, reducing the scan rate compared with more aggressive timing templates.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Executed a T2 timing scan against the seven known ports and compared the identified ports and completion time with previous scans.

## Output Summary
All seven ports were again reported open. The T2 scan completed in approximately 3.91 seconds.

## Observation
The slower timing scan identified the same open ports while taking longer than the SYN and TCP Connect scans recorded in this project.

## Conclusion
The slow timing scan successfully confirmed the open ports and demonstrated the effect of Nmap timing configuration on scan duration.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

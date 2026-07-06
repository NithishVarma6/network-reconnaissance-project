# Task 2: Full TCP Port Scan

## Objective
Scan all 65,535 TCP ports on the authorized target to identify exposed TCP services.

## Command Used
```bash
nmap -p- -oN raw-output/full-port-scan.txt 10.48.84.93
```

## Command Explanation
`-p-` instructs Nmap to scan every TCP port from 1 to 65535. `-oN` stores the output in a text file.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Executed a complete TCP port scan against the confirmed active target and reviewed the returned port states.

## Output Summary
Seven open TCP ports were identified: 22, 53, 139, 445, 7777, 7778, and 8443. Nmap reported 65,528 closed TCP ports.

## Observation
The target exposed SSH, domain-related, NetBIOS/SMB, and high-numbered web or application ports.

## Conclusion
The full TCP scan successfully established the target's open-port attack surface for further service enumeration.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

# Task 1: Host Discovery

## Objective
Identify whether the authorized TryHackMe lab target is active before performing port scanning.

## Command Used
```bash
nmap -sn -oN raw-output/host-discovery.txt 10.48.84.93
```

## Command Explanation
`-sn` performs host discovery without a port scan. `-oN` saves the result in normal Nmap format.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Opened the Kali Linux terminal, confirmed the authorized lab target IP, executed the host discovery command, and reviewed the response to verify host availability.

## Output Summary
The target 10.48.84.93 was reported as up with approximately 0.061 seconds latency. One IP address was scanned and one host was up.

## Observation
The target responded successfully and was reachable from the scanning system.

## Conclusion
Host discovery was completed successfully. The active host was confirmed before continuing with detailed reconnaissance.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

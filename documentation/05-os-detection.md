# Task 5: Operating System Detection

## Objective
Use TCP/IP fingerprinting to attempt identification of the target operating system.

## Command Used
```bash
nmap -O -oN raw-output/os-detection.txt 10.48.84.93
```

## Command Explanation
`-O` enables Nmap operating system detection using network fingerprinting techniques.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Executed Nmap OS detection against the active target and reviewed the fingerprint and network-distance information.

## Output Summary
Nmap did not return an exact OS match. It generated a TCP/IP fingerprint and reported the network distance as three hops.

## Observation
Although an exact OS match was unavailable, service information from the earlier scan indicated a Linux environment.

## Conclusion
OS fingerprinting was attempted successfully, but the scan result was inconclusive for an exact operating system match.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

# Task 4: Manual HTTP Banner Grabbing

## Objective
Manually verify the HTTP server banner and compare it with automated Nmap service detection.

## Command Used
```bash
curl -I http://10.48.84.93:7777
```

## Command Explanation
`curl -I` requests HTTP response headers only, allowing the web server banner and header information to be reviewed.

## Procedure
1. Opened the Kali Linux terminal in the authorized TryHackMe lab environment.
2. Confirmed the target IP address as `10.48.84.93`.
3. Executed the Nmap or curl command shown above.
4. Saved or reviewed the command output.
5. Analyzed the returned host, port, service, or response information.

Sent an HTTP HEAD request to the web service on port 7777 and inspected the returned response headers.

## Output Summary
The server returned `HTTP/1.1 200 OK` and the `Server` header identified `nginx/1.28.2`. Other headers included Content-Type, Content-Length, Last-Modified, ETag, and Accept-Ranges.

## Observation
The manual banner confirmed the nginx 1.28.2 result reported by Nmap on port 7777.

## Conclusion
Manual HTTP banner grabbing successfully validated the automated service-version result.

## Evidence
The original command output is available in the repository's `raw-output/` directory.

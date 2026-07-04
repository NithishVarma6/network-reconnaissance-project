# Network Scanning Commands

## 1. Host Discovery

sudo nmap -sn 10.48.84.93 -oN raw-output/host-discovery.txt

## 2. Full TCP Port Scan

sudo nmap -p- 10.48.84.93 -oN raw-output/full-port-scan.txt

## 3. Service and Version Detection

sudo nmap -sV -p 22,53,139,445,7777,7778,8443 10.48.84.93 -oN raw-output/service-version.txt

## 4. Manual HTTP Banner Grabbing

curl -I http://10.48.84.93:7777

curl -I http://10.48.84.93:7777 2>&1 | tee raw-output/http-banner.txt

## 5. OS Detection

sudo nmap -O 10.48.84.93 -oN raw-output/os-detection.txt

## 6. SYN Scan

time sudo nmap -sS -p 22,53,139,445,7777,7778,8443 10.48.84.93 -oN raw-output/syn-scan.txt

## 7. TCP Connect Scan

time sudo nmap -sT -p 22,53,139,445,7777,7778,8443 10.48.84.93 -oN raw-output/connect-scan.txt

## 8. Packet Fragmentation Scan

sudo nmap -f -p 22,53,139,445,7777,7778,8443 10.48.84.93 -oN raw-output/fragment-scan.txt

## 9. Slow Timing Scan

time sudo nmap -T2 -p 22,53,139,445,7777,7778,8443 10.48.84.93 -oN raw-output/slow-scan.txt


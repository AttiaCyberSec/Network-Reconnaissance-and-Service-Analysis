# Network Reconnaissance and Service Analysis

## Objective
To perform basic network reconnaissance on a Kali Linux virtual machine. Identify open ports, running services, and test network connectivity.

## Tools Used
Apache2, nmap, netstat, netcat, ping, traceroute

## Procedure and Results

### Step 1: Start Apache
```bash
sudo service apache2 start
curl http://localhost
```
**Result:** Apache server started successfully

### Step 2: Nmap Scan
```bash
nmap -sV -sC localhost
```
### Step 3: Check Listening Services
```bash
netstat -tulpn
```
Result: apache2 listening on 0.0.0.0:80

### Step 4: Banner Grabbing
```bash
nc localhost 22
nc localhost 80
```
Result: SSH refused, HTTP 403 Forbidden

### Step 5: Ping and Traceroute
```bash
ping -c 4 8.8.8.8
traceroute 8.8.8.8
```
Result:75% packet loss, First hop: 10.0.2.2

## Network Map
```bash
[ Kali Linux VM ]
   IP: 127.0.0.1 / 10.0.2.15
           |
     Port 80/TCP - OPEN
           |
  Apache httpd 2.4.68 (Debian)
```

## Conclusion
Basic network reconnaissance and service enumeration completed successfully.

# Network Reconnaissance Labs

Hands-on labs I completed while learning cybersecurity (started September 2026). They cover the basic tools used to gather information about domains, networks and hosts.

**Tools used:** nslookup, who.is, ipconfig, netstat, nmap, ping

**Environments:** Windows 10, Kali Linux
## Projects

### 01. DNS and WHOIS reconnaissance
Looked up `example.com` using NsLookup.io and who.is to find its DNS records, IP addresses and registration details.
**What I learned:** A domain can have more than one IP address. `example.com` returned two A records (172.66.147.243 and 104.20.23.154), which explains why my ping results showed different IPs on different machines.

### 02. Checking IP addresses and network connections
Used `ipconfig` to view my network adapters, IP address and subnet mask, and `netstat` to see active connections on my machine.
**What I learned:** How to read connection states such as ESTABLISHED, CLOSE_WAIT and TIME_WAIT, and how to spot which remote addresses my computer is talking to.

### 03. Basic Nmap scans
Ran three scans against `scanme.nmap.org`, a server provided by the Nmap project for legal practice:
- `nmap scanme.nmap.org`: default scan. Found ports 22 (ssh) and 80 (http) open, and 25 and 587 filtered.
- `nmap -sn scanme.nmap.org`: host discovery only, no port scan.
- `nmap -p80 scanme.nmap.org`: scan of one specific port.

**What I learned:** The difference between open, closed and filtered ports, and how scan options change the amount of information gathered. I also made a typo (`nmap-sn`) and learned that a missing space gives "command not found".

### 04. Testing connectivity with ping
Pinged `google.com` and `example.com` on Windows (4 packets, 0% loss) and `example.com` on Kali Linux (continuous ping until stopped).
**What I learned:** How to read response time, TTL and packet loss, and how Windows and Linux ping behave differently by default.

## Ethical note
All scans were run only on systems I own or that are provided for practice.

## Next steps
Wireshark traffic analysis, Wazuh log monitoring and Python security scripts.

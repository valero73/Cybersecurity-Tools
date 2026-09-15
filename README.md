# 50 Cybersecurity Tools — The Ultimate Arsenal

Practical commands, real examples, and use cases across reconnaissance, web security, networks, forensics, OSINT, wireless, passwords, and more.

> Compiled from the [CyberKid / Anastasis Vasileiadis](https://x.com/Anastasis_King) cybersecurity roadmap carousel: [50 CYBERSECURITY TOOLS](https://x.com/Anastasis_King/status/2099728328580022291).

**Use these tools only on systems you own or have explicit written authorization to test.** Unauthorized access, interception, or exploitation is illegal.

---

## Category 1 — Reconnaissance

Find. Map. Understand. Gather information and discover the attack surface.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **Nmap** | `nmap -sS -sV -O -p- target.com` | Network mapping — scan ports, detect services and operating systems |
| 2 | **Masscan** | `masscan -p1-65535 --rate 1000 target.com` | Fast network scanning for large networks |
| 3 | **RustScan** | `rustscan -a target.com -- -sV` | Modern, fast port scanner built on Nmap |
| 4 | **Zmap** | `zmap -p 80 target.com` | Internet-wide scanner for large-scale research |
| 5 | **Amass** | `amass enum -d target.com` | In-depth subdomain enumeration and asset discovery |
| 6 | **Subfinder** | `subfinder -d target.com -all -silent` | Find subdomains from multiple sources |
| 7 | **Assetfinder** | `assetfinder --subs-only target.com` | Discover domains and subdomains from public sources |
| 8 | **theHarvester** | `theHarvester -d target.com -b all` | Gather emails, subdomains, hosts from public sources |
| 9 | **Shodan** | `shodan search "apache"` | Search for internet-connected devices and services |
| 10 | **Fofa** | `fofa search 'domain="target.com"'` | Search for exposed services, devices, and vulnerabilities |

---

## Category 2 — Web Application Assessment

Find vulnerabilities. Secure the web. Enumerate, scan, analyze, report.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **Burp Suite** | `burpsuite` | Intercept, analyze, and modify web traffic — industry standard |
| 2 | **Nikto** | `nikto -h target.com` | Scan web servers for known vulnerabilities |
| 3 | **Wapiti** | `wapiti -u https://target.com -m all` | Black-box web vulnerability scanner |
| 4 | **sqlmap** | `sqlmap -u "https://target.com/page.php?id=1" --batch` | Detect and exploit SQL injection vulnerabilities |
| 5 | **commix** | `commix -u "https://target.com/page.php?id=1" --batch` | Automated command injection exploitation tool |
| 6 | **WPScan** | `wpscan --url https://target.com --enumerate u` | Scan WordPress sites for vulnerabilities |
| 7 | **Dirb** | `dirb https://target.com /usr/share/dirb/wordlists/common.txt` | Brute-force directories and files |
| 8 | **Gobuster** | `gobuster dir -u https://target.com -w /usr/share/wordlists/dirb/common.txt` | Fast directory/file enumeration |
| 9 | **ffuf** | `ffuf -u https://target.com/FUZZ -w wordlist.txt` | Fast web fuzzer for parameter discovery |
| 10 | **WhatWeb** | `whatweb https://target.com` | Identify technologies used by a website |

---

## Category 3 — Network Analysis & Monitoring

See the traffic. Find the truth. Secure the network.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **Wireshark** | *(GUI)* | Graphical network protocol analyzer — inspect live or saved traffic |
| 2 | **tcpdump** | `tcpdump -i eth0 -w capture.pcap` | Capture network packets from an interface |
| 3 | **tshark** | `tshark -i eth0 -Y "http"` | Command-line Wireshark — filter and analyze traffic |
| 4 | **ettercap** | `ettercap -T -q -i eth0 -M arp:remote //target1// /target2//` | Network sniffer and MITM tool for analysis and ARP testing |
| 5 | **bettercap** | `bettercap -iface eth0` | Framework for network analysis, monitoring, and security testing |
| 6 | **Nmap** | `nmap -sn 192.168.1.0/24` | Discover live hosts in a network (ping scan) |
| 7 | **Zenmap** | `zenmap` | GUI for Nmap — easier scanning and visualization |
| 8 | **iperf3** | `iperf3 -s` / `iperf3 -c <ip>` | Measure network bandwidth and performance |
| 9 | **mtr** | `mtr -rw target.com` | Combine ping and traceroute for real-time path diagnostics |
| 10 | **iftop** | `iftop -i eth0` | Show real-time bandwidth usage per host |

---

## Category 4 — Vulnerability Scanning

Find weaknesses. Fix them. Stay secure.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **Nessus** | `nessuscli scan --policy "Basic" --target <IP>` | Professional vulnerability scanner |
| 2 | **OpenVAS** | `openvas-cli --scan --target <IP> --profile Full` | Open-source vulnerability scanner (GVM) |
| 3 | **Nuclei** | `nuclei -u https://target.com -t cves/ -severity high` | Fast template-based vulnerability scanner |
| 4 | **Nikto** | `nikto -h https://target.com -Tuning b` | Scan web servers for known vulnerabilities |
| 5 | **WPScan** | `wpscan --url https://target.com --enumerate vp` | Scan WordPress sites for vulnerabilities and plugins |
| 6 | **SQLMap** | `sqlmap -u "http://target.com/page.php?id=1" --batch` | Automate SQL injection detection and exploitation |
| 7 | **OWASP ZAP** | `zap-cli quick-scan --self-contained -t <url>` | Automated web application security testing |
| 8 | **Acunetix** | `acunetix_cli scan --target <url> --profile full` | Commercial web vulnerability scanner |
| 9 | **Trivy** | `trivy image target/image:latest` | Scan containers, images, and files for vulnerabilities |
| 10 | **ClamAV** | `clamscan -r /path/to/scan` | Open-source antivirus for malware detection |

---

## Category 5 — Cloud & OSINT

Gather. Analyze. Connect the dots.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **theHarvester** | `theHarvester -d target.com -b all` | Gather emails, subdomains, hosts from public sources |
| 2 | **Maltego** | `maltego` | Visualize relationships between people, domains, and data |
| 3 | **Recon-ng** | `recon-ng` | Modular framework for OSINT reconnaissance |
| 4 | **SpiderFoot** | `spiderfoot -s target.com` | Automated OSINT for domains, IPs, emails, and more |
| 5 | **Sherlock** | `sherlock username` | Find social media accounts by username across hundreds of sites |
| 6 | **Holehe** | `holehe username` | Check if an email or username exists on multiple platforms |
| 7 | **HIBP** | `hibp-breach-check email@example.com` | Check if an email has been exposed in known data breaches |
| 8 | **Have I Been Pwned** | `curl https://haveibeenpwned.com/api/v3/breachedaccount/your@email.com` | Query HIBP API for breach information |
| 9 | **DNSRecon** | `dnsrecon -d target.com -t std` | DNS enumeration (subdomains, records, zone transfer checks) |
| 10 | **Amass** | `amass enum -d target.com` | In-depth OSINT and subdomain enumeration |

---

## Category 6 — Password Attacks & Cracking

Test strength. Audit security. Protect accounts. Only on systems you are authorized to test.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **Hashcat** | `hashcat -m 0 hashes.txt -a 0 wordlist.txt` | Fast password cracker (GPU accelerated) |
| 2 | **John the Ripper** | `john --wordlist=rockyou.txt hashes.txt` | Classic password cracker (many hash types) |
| 3 | **Hydra** | `hydra -l admin -P passwords.txt ssh://192.168.1.1` | Network login auditing across multiple protocols |
| 4 | **Medusa** | `medusa -h 192.168.1.1 -u admin -P pass.txt -M ssh` | Fast, parallel login auditing |
| 5 | **Ncrack** | `ncrack -u admin -P pass.txt ssh://192.168.1.1` | Network authentication testing (Nmap project) |
| 6 | **CeWL** | `cewl -d 2 -m 5 https://target.com -o wordlist.txt` | Generate custom wordlists from websites |
| 7 | **Crunch** | `crunch 8 8 abc123 -o custom.txt` | Create custom wordlists with patterns |
| 8 | **RSMangler** | `rsmangler -f wordlist.txt -r rules.txt -o newlist.txt` | Modify wordlists with advanced mangling rules |
| 9 | **CUPP** | `cupp -i` | Create personalized wordlists from public information |
| 10 | **Patator** | `patator ssh_login host=192.168.1.1 user=admin password=FILE0 0=pass.txt` | Multi-protocol brute-force tool |

---

## Category 7 — Wireless & Mobile Security

Scan. Analyze. Protect. Stay ahead. Only on networks you own or are authorized to test.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **Aircrack-ng** | `aircrack-ng -w wordlist.txt capture.cap` | Crack WEP/WPA keys from captured handshakes |
| 2 | **Airodump-ng** | `airodump-ng wlan0 --write capture` | Capture Wi-Fi traffic (handshake) |
| 3 | **Aireplay-ng** | `aireplay-ng -0 10 -a <BSSID> -c <CLIENT> wlan0` | Deauthentication attack (authorized Wi-Fi testing) |
| 4 | **Wifite** | `wifite --interface wlan0 --dict wordlist.txt` | Automated Wi-Fi auditing tool |
| 5 | **Kismet** | `kismet -c wlan0` | Passive wireless network detector and sniffer |
| 6 | **Reaver** | `reaver -i wlan0 -b <BSSID> -vv` | WPS security test (authorized only) |
| 7 | **Wash** | `wash -i wlan0` | Scan for WPS-enabled routers |
| 8 | **Wigle** | `wigle --gps --interface wlan0` | Collect and upload Wi-Fi data to Wigle.net |
| 9 | **bluetoothctl** | `bluetoothctl scan on` | Discover nearby Bluetooth devices |
| 10 | **MobSF** | `mobsf` | Mobile application security testing (static and dynamic) |

---

## Category 8 — Digital Forensics & Incident Response

Investigate. Respond. Recover.

| # | Tool | Example command | Purpose |
|---|------|-----------------|---------|
| 1 | **Autopsy** | `autopsy` | Open-source digital forensics platform (GUI) |
| 2 | **Volatility** | `vol.py -f memory.dmp windows.info` | Analyze memory dumps for malware, processes, and evidence |
| 3 | **FTK Imager** | `ftkimager.exe` | Create forensic images (DD, E01) of storage devices |
| 4 | **ExifTool** | `exiftool file.jpg` | View and edit metadata from images, documents, and more |
| 5 | **Binwalk** | `binwalk -e firmware.bin` | Analyze and extract files from firmware images |
| 6 | **Foremost** | `foremost -i image.dd -o output/` | Recover deleted files from disk images |
| 7 | **Strings** | `strings file.bin | less` | Extract readable strings from binary files |
| 8 | **Steghide** | `steghide extract -f image.jpg` | Detect and extract hidden data in images |
| 9 | **Bulk Extractor** | `bulk_extractor image.dd -o out/` | Scan disk images for emails, URLs, and other artifacts |
| 10 | **CyberChef** | *(web tool)* | Analyze, decode, and transform data online |

---

## Recap — Core stack worth knowing first

These show up repeatedly across workflows:

| Tool | Why it matters |
|------|----------------|
| **Linux** | The foundation for most security tooling |
| **Nmap** | Host and service discovery |
| **Wireshark / tshark** | Packet-level truth |
| **Burp Suite** | Web traffic interception and testing |
| **Gobuster / ffuf** | Content and directory discovery |
| **sqlmap** | Authorized SQL injection testing |
| **Metasploit** | Exploitation framework (authorized testing only) |
| **Docker / Kubernetes** | Isolated labs and container security |
| **Aircrack-ng** | Authorized wireless assessments |
| **Hashcat / John** | Password-strength auditing |

Example lab helpers from the original series:

```bash
docker run -it kali/kali-rolling
kubectl get pods
msfconsole
chmod +x script.sh && ./script.sh
```

---

## Ethics

- Knowledge is power. Ethics is the shield.
- Practice on labs, CTFs, bug-bounty programs, and assets you are contracted to test.
- Do not run offensive commands against third-party systems without permission.

## Source

Original carousel by **Anastasis Vasileiadis** (@Anastasis_King / CyberKid):

- https://x.com/Anastasis_King/status/2099728328580022291

Tags from the original post: `#CyberSecurity` `#CyberSecurityTools` `#EthicalHacking` `#InfoSec` `#CyberKid`

<div align="center">

# 🔐 Cybersecurity Lab - PENETRATION TESTING REPORT

**Penetration testing and ethical hacking practice**

**W2-PM1: Footprinting with multiple Kali tools (6 tools on networkwalks.com) & W2-PM5: Zenmap based Network Scanning**
</div>

<p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ver-Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.3-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Linux-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Virtualization-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Windows%2011-E87500?style=flat-square&labelColor=000000&logo=PCGamingWiki&logoColor=white" />
  <img src="https://img.shields.io/badge/Skill-Reconnaissance%20&%20Footprinting-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Skill-Scanning%20&%20Network%20Discovery-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Zenmap%20v7.99-0070C0?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/AZIAGBEDO%20KOKOU%20SODJINE%20-%20CCEP-C00000?style=flat-square" />
</p>

---

# 📘Penetration Testing Report
### 🫆👣Footprinting & 🔍Network Scanning Phases

**W2-PM-FINAL  |  CYBERSECURITY  |  NETWORKWALKS**

| Field | Detail |
|---|---|
| **Pentester Name (Cybersecurity Professional)** | **AZIAGBEDO KOKOU SODJINE** |
| **Program/Batch** | B084-Networkwalks |
| **Date** | 10 November 2026 |
| **Modules completed** | W2-PM1 (Multiple Kali Tools)<br>W2-PM5 (Zenmap Scanning) |
| **Client/Target** | 1. Networkwalks (secured written permission already)<br>2. My own local LAN Network |
| **Permission secured from client?** | Yes |
| **Phases covered** | **Phase 1:** Reconnaissance & Footprinting<br>**Phase 2:** Scanning & Network Discovery<br>**Phase 3-5:** In Progress |

---

# 1. Liability Disclaimer

I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. 

Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorised access is a crime even when nothing is damaged.

---

# 2. Introduction

This report covers footprinting the networkwalks.com domain using multiple Kali Linux tools (W2-PM1) and scanning my own local network with Zenmap (W2-PM5). One module covers the footprinting phase and the other covers the scanning phase, so together they show how an attacker moves from gathering public information to mapping live hosts on a network. These activities are part of the Week 2 of my internship program at Networkwalks.

All commands were run in Kali Linux (footprinting and scanning). Every step below includes the exact command used, the result I observed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view. The commands outputs are also saved in text files that are available in "/outputs_files" as well as the zenmap topology pdf file.

---

# 3. Tools Used

The table below lists each tool used in this report and its purpose.

| Tool | Purpose |
|---|---|
| Kali Linux & Windows | Operating systems used in the lab for footprinting and reconnaissance activities|
| WHOIS                | Find domain registration details (owner, dates, name servers).   |
| whatweb              | Fingerprint web technologies (server, CMS, plugins, IP).         |
| nslookup             | Resolve the domain name to its IP address using DNS.             |
| curl -I              | Read the HTTP response headers of the website.                   |
| wafw00f              | Detect whether a Web Application Firewall protects the site.     |
| dnsrecon             | Enumerate all DNS records (NS, MX, SPF, TXT, SRV).               |
| Zenmap (Nmap GUI)    | Scan the local subnet to find live hosts, IPs and MAC addresses. |
| Linux & Windows CMD | Local IP and MAC address identification / confirmation            |

---

# 4. Activities Performed

---

## 4.1 Footprinting & Reconnaissance

I performed reconnaissance against the `networkwalks.com` domain using six Kali Linux tools: **WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon**. Each tool was used to collect a different type of information about the target.

First, I used **WHOIS** to obtain publicly available domain registration information and identify the domain’s name servers. The results provided information about the domain registration and hosting infrastructure.

I then used **WhatWeb** to identify technologies used by the website. The results identified **WordPress 7.1.4**, **WordPress Download Manager 3.3.76**, **Bootstrap 7.1.4** and **JQuery 3.7.1**, along with other informations exposed by the website.

Using **Nslookup**, I resolved the domain name to its IP address. The provided result identified **192.232.216.135**.

I used **Curl** with the `-I` option to inspect the HTTP response headers. This provided additional information about the web application and exposed the WordPress REST API endpoint `/wp-json/`.

Next, I used **Wafw00f** to determine whether a Web Application Firewall was protecting the website. The result identified **ModSecurity (SpiderLabs)**.

Finally, I used **DNSRecon** to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.

---

## 4.2 Network Scanning with Zenmap

For the second activity, I launched the GUI of **Zenmap** from my Kali Linux. I used Zenmap to perform network discovery on my local network. The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.

I first used the `ifconfig -a` command on the Kali VM to identify my local IP address (**`10.0.0.2`**) and LAN subnet (**`10.0.0.0/24`**). I then entered the subnet into Zenmap and selected **`Ping Scan`** to identify active hosts. 

And I scanned with the command : 

````bash
nmap -sn 10.0.0.0/24
````

The results identified three live hosts:

- `10.0.0.1`
- `10.0.0.7`
- `10.0.0.2`

The results also included two MAC addresses.

|Live Hosts       | IP Address | MAC Address | Local VM Name |
|-----------------|------------|-------------|---------------|
|QEMU virtual NIC | 10.0.0.1 | 52:54:00:12:35:00 | Gateway |
|Oracle VirtualBox virtual NIC | 10.0.0.7| 08:00:27:CE:C9:16 | Windows7 VM |
|Zenmap Host  | 10.0.0.2 | 08:00:27:08:12:48| KALI_LINUX VM |

After completing the scan, I opened the **Topology** section in Zenmap, enabled the legend and saved the network topology in PDF format. The topology pdf file is available at /outputs_files/9_zenmap_topology.pdf

**Note:** The actual subnet, number of hosts and addresses should be replaced with the results from my own network when submitting the report.

---

# 5. Risk Analysis / Impact

Based on the information collected during the footprinting and network scanning activities, I identified the following potential risks.

| **\#** | **Risk / Finding**                           | **Evidence / Observation**                                  | **Potential Impact**                                                                                            | **Risk Level** |
|--------|----------------------------------------------|-------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|----------------|
| 1      | Web technology information exposed           | WhatWeb identified WordPress and WP Download Manager        | Attackers may use exposed technology/version information to identify software requiring further security review | **🟠 Medium**   |
| 2      | Server IP address identifiable               | Nslookup resolved the domain to `192.232.216.135`           | Provides information about the network location of the web service                                              | **🟡 Low**      |
| 3      | HTTP technical information exposed           | Curl returned HTTP response headers and exposed `/wp-json/` | May assist technology fingerprinting and further enumeration                                                    | **🟡 Low**      |
| 4      | WAF technology identifiable                  | Wafw00f identified ModSecurity (SpiderLabs)                 | Reveals information about the web application’s security architecture                                           | **🟡 Low**      |
| 5      | DNS infrastructure information exposed       | DNSRecon identified DNS, mail and service-related records   | DNS information can help build a broader infrastructure profile                                                 | **🟠 Medium**   |
| 6      | Multiple live hosts visible on local network | Zenmap identified three live hosts in the example network    | Unknown or unauthorized devices may potentially be present on a network                                         | **🟠 Medium**   |

**Risk level key:** 🔴 Critical 🟠 Medium 🟡 Low

The risks above are observations from the footprinting and scanning exercises, not confirmed vulnerabilities.

The practical exercises primarily involved information gathering and host discovery. No exploitation or vulnerability validation was performed as part of these two modules.

Therefore, the presence of information such as a software version, IP address or DNS record does not by itself mean that the system is vulnerable. Further authorized security testing would be required to confirm any actual vulnerability.

---

# 6. Recommendations

Based on the observations from these activities, I recommend the following security improvements:

1.  **Review publicly exposed technology information**  
    Organizations should regularly review what information about their web technologies, CMS and plugins is publicly visible.

2.  **Keep software updated**  
    CMS platforms, plugins and other web technologies should be regularly updated and reviewed against current security advisories.

3.  **Review HTTP headers**  
    HTTP response headers should be reviewed to determine whether unnecessary technical information is being exposed.

4.  **Review DNS records regularly**  
    DNS records should be checked periodically to ensure that only required information and services are publicly exposed.

5.  **Properly configure and monitor the WAF**  
    Keep the WAF (ModSecurity) enabled and tuned, since it already blocks naive attacks.

6.  **Perform regular internal network discovery**  
    Organizations should periodically scan their own networks to identify active devices.

7.  **Investigate unknown devices**  
    Any unexpected device discovered during network scanning should be investigated and verified.

8.  **Maintain network documentation**  
    Network topology and device information should be documented and updated regularly.

9.  **Perform security testing with authorization**  
    Reconnaissance and scanning should only be performed against systems and networks where appropriate authorization has been provided.

---

# 7. Conclusion

During Week 2 of my Cybersecurity & Ethical Hacking internship, I completed practical activities covering footprinting, reconnaissance and network scanning.

In the footprinting activity, I used six Kali Linux tools to collect information about the target domain. I demonstrated how WHOIS can provide domain information, WhatWeb can identify web technologies, Nslookup can resolve domain names, Curl can inspect HTTP headers, Wafw00f can identify a WAF, and DNSRecon can provide additional DNS information.

In the network scanning activity, I used Zenmap to identify my local network configuration and discover active hosts. I also collected IP and MAC address information and created a network topology.

The exercises showed that information gathering is an important part of cybersecurity. Even before attempting to exploit a system, a security professional can gather a significant amount of information on an environment by carefully analyzing publicly available information and network responses.

I also demonsrated that technical findings should be documented clearly. A good cybersecurity report should explain what was performed, what was discovered, what the observation means, what risk it may create, and what can be done to reduce that risk.

Finally, I demonstrated that reconnaissance and scanning must always be performed within an authorized scope. These activities were completed as part of the Networkwalks Cybersecurity internsgip program.

---

# 8. Evidences Collected

---

## 📷Screenshots

*Screenshots collected as evidence during the activities (stored in the **`/screenshots/`** folder):*

![whois output](/screenshots/1_whois.png)

![whatweb output](/screenshots/2_whatweb.png)

![nslookup output](/screenshots/3_nslookup.png)

![curl output](/screenshots/4_curl.png)

![wafw00f output](/screenshots/5_wafw00f.png)

![dnsrecon output](/screenshots/6_dnsrecon.png)

![zenmap output](/screenshots/7_zenmap.png)

![loacal_mac output](/screenshots/8_ifconfig-a.png)

![windows_mac output](/screenshots/ipconfig_all.png)

![Zenmap scan and topology](/screenshots/9_topology.png)

---

## 📄Output files

*The outputs of executed commands are saved in files as evidence during the activities (stored in the **`/outputs_files/`** folder):*

### The /outputs_files/ folder content 

---

|Output File| Command |
|-------|--------|
| ├─ 📂outputs_files|Folder|
| ├── [1_whois.txt](/outputs_files/1_whois.txt) | `whois networkwalks.com` |    
├── [2_whatweb.txt](/outputs_files/2_whatweb.txt)     |  `whatweb networkwalks.com` 
├── [3_nslookup.txt](/outputs_files/3_nslookup.txt)    |      `nslookup networkwalks.com`
├── [4_curl.txt](/outputs_files/4_curl.txt)         |  `curl -I https://networkwalks.com`                
├── [5_wafw00f.txt](/outputs_files/5_wafw00f.txt)       |  `wafw00f networkwalks.com`            
├── [6_dnsrecon.txt](/outputs_files/6_dnsrecon.txt)       | `dnsrecon -d networkwalks.com`        
├── [7_zenmap.txt](/outputs_files/7_zenmap.txt) |  `nmap -sn 10.0.0.0/24`
├── [8_ifconfig-a.txt](/outputs_files/8_ifconfig-a.txt)     | `ifconfig -a`
└── [9_zenmap_topology.pdf](/outputs_files/9_zenmap_topology.pdf)  | `Topology -> Save Graphic`


-End-

---

# 👤 Author

**AZIAGBEDO KOKOU SODJINE**\
Cybersecurity Professional B084

LinkedIn: https://www.linkedin.com/in/kokou-sodjin%C3%A8-aziagbedo-434b2949

---

## 📌 Project Information

**Program Name:** Cybersecurity at Networkwalks | **Week:** 02 | **Project:** Footprinting & Reconnaissance Attacks With Multiple KALI Tools | **Repository:** GitHub


# Cybersecurity Learning Journey

This is where I keep track of what I learn as I build my cybersecurity skills. I am keeping the notes in the same place and in the same order I learned them, so it feels like an actual journey rather than a collection of random notes.

I will keep adding new days as I learn, practice labs, and work on projects.

---

## Day 1: OSI Model and Networking Basics

Today I started with the OSI model. I learned that network communication can be understood through seven different layers, with each layer handling a different part of the communication process.

### The 7 Layers

| Layer | Name | Examples | What it does |
|---|---|---|---|
| 7 | Application | HTTP, HTTPS, DNS, FTP, SSH | Provides network services to applications and users |
| 6 | Presentation | SSL/TLS, JPEG | Handles encryption, encoding, and compression |
| 5 | Session | NetBIOS, RPC | Establishes and manages communication sessions |
| 4 | Transport | TCP, UDP | Handles delivery, reliability, and port numbers |
| 3 | Network | IP, ICMP | Handles IP addressing and routing |
| 2 | Data Link | Ethernet, ARP | Handles MAC addresses and local network delivery |
| 1 | Physical | Wi-Fi, cables | Carries bits and signals through the physical medium |

The mnemonic I used to remember the layers from 7 to 1 is **All People Seem To Need Data Processing**.

### Private and Public IP Addresses

I also learned the difference between private and public IP addresses. Private IP addresses are used inside local networks, such as `192.168.x.x`, `10.x.x.x`, and `172.16.x.x` to `172.31.x.x`. A public IP address is assigned by an ISP and is used when communicating over the internet.

I also learned about **NAT (Network Address Translation)**. The router can translate private IP addresses into a public IP address when traffic leaves the local network.

### What I Practiced

I completed the TryHackMe **"What is Networking?"** room to practice the concepts I learned.

---

## Day 2: TCP, UDP, Ports, DNS, and HTTP/HTTPS

Today I continued with networking and started looking more closely at how communication actually happens. I learned about TCP and UDP, the TCP three-way handshake, common ports, DNS, HTTP and HTTPS, and what happens behind the scenes when I visit a website.

### TCP vs UDP

The main difference I understood is that TCP focuses on reliable delivery, while UDP focuses more on speed and lower overhead.

| | TCP | UDP |
|---|---|---|
| Reliable | Yes | No |
| Speed | Generally slower | Generally faster |
| Handshake | Yes | No |
| Examples | HTTP, SSH, FTP, SMTP | DNS, streaming, VoIP, games |
| Use when | Accuracy matters | Speed matters more |

### TCP 3-Way Handshake

I learned that a TCP connection starts with three steps:

1. **SYN:** The client requests a connection and sends a sequence number.
2. **SYN-ACK:** The server acknowledges the request and sends its own sequence number.
3. **ACK:** The client acknowledges the server and the connection is established.

This also introduced me to the security side of the process. A **SYN flood** can abuse the connection process by sending many SYN requests without completing the handshake, potentially consuming the server's available connection resources.

### Common Ports

I started learning common ports because they are important when identifying services during network enumeration.

| Port | Protocol | Main use |
|---|---|---|
| 21 | FTP | File transfer |
| 22 | SSH | Secure remote access |
| 23 | Telnet | Remote access without encryption |
| 25 | SMTP | Sending email |
| 53 | DNS | Domain name resolution |
| 80 | HTTP | Web traffic |
| 110 | POP3 | Receiving email |
| 143 | IMAP | Email access and management |
| 443 | HTTPS | Encrypted web traffic |
| 445 | SMB | Windows file and printer sharing |
| 1433 | MSSQL | Microsoft SQL Server |
| 3306 | MySQL | MySQL database connections |
| 3389 | RDP | Remote Desktop |
| 8080 | HTTP-Alt | Alternative web applications |
| 9200 | Elasticsearch | Elasticsearch HTTP interface |

I also started connecting these ports to security risks. For example, FTP and Telnet do not provide the same protection as encrypted protocols, while services such as SSH, RDP, and SMB can become security risks when they are poorly configured or exposed unnecessarily.

### DNS

I learned how DNS translates a domain name into an IP address. In a simplified example, when I enter `google.com`, my computer asks a DNS resolver for the address. The resolver follows the DNS hierarchy until it finds the appropriate authoritative server, which returns the IP address that the browser can connect to.

I also learned about **DNS poisoning**, where an attacker can cause a domain to resolve to a malicious IP address instead of the legitimate one.

### HTTP vs HTTPS

I learned that HTTP normally uses port 80, while HTTPS normally uses port 443 and uses TLS to protect the connection.

One important point I learned is that HTTPS protects the communication channel, but it does not automatically make the website itself secure. Vulnerabilities such as SQL injection and XSS can still exist in an HTTPS application.

### How a Website Works

I started putting the networking concepts together by looking at what happens when a website loads:

**Browser → Web request → Web server → Application → Database → Web server → Browser**

The browser sends a request, the server processes it, the application may communicate with a database, and the response is eventually returned to the browser.

### Commands I Practiced

```bash
ipconfig
ping google.com
tracert google.com
nslookup google.com
netstat -an
```

These commands helped me start getting comfortable with checking network information, testing connectivity, following network routes, resolving domains, and viewing network connections.

### What I Completed

- [x] TryHackMe: **What is Networking?**
- [x] TryHackMe: **DNS in Detail**
- [x] TryHackMe: **HTTP in Detail**
- [x] TryHackMe: **Networking Concepts**
- [x] TryHackMe: **Networking Core Protocols** theory
- [x] **How Websites Work** theory

---

## Day 3

*Coming next...*

I will continue adding the next day here as I move forward with networking, Linux, Python, cybersecurity labs, and eventually more practical security work.

# Cybersecurity Learning Journey

This file documents my learning progress day by day. I am keeping the notes together so I can see how one topic connects to the next instead of treating every subject as a separate document.

---

## Day 1: Getting Started with Networking and the OSI Model

Today I started building my networking foundation by learning about the OSI model. The main idea behind the model is to break network communication into seven layers, with each layer handling a different part of the communication process.

### The 7 Layers

| Layer | Name | Examples | What I understood |
|---|---|---|---|
| 7 | Application | HTTP, HTTPS, DNS, FTP, SSH | Where network services interact with applications and users |
| 6 | Presentation | SSL/TLS, JPEG | Handles things such as encryption, encoding, and compression |
| 5 | Session | NetBIOS, RPC | Helps establish and manage communication sessions |
| 4 | Transport | TCP, UDP | Handles end-to-end communication, reliability, and port numbers |
| 3 | Network | IP, ICMP | Responsible for addressing and routing between networks |
| 2 | Data Link | Ethernet, ARP | Handles MAC addresses and communication within the same network |
| 1 | Physical | Wi-Fi, cables | Carries the actual bits and signals through the physical medium |

A mnemonic that helped me remember the layers from 7 to 1 is **All People Seem To Need Data Processing**.

### Private and Public IP Addresses

I also learned the difference between private and public IP addresses. Private addresses are used inside local networks, such as `192.168.x.x`, `10.x.x.x`, and `172.16.x.x` through `172.31.x.x`. A public IP address is assigned by an ISP and is used when communicating over the internet.

I also learned about **NAT (Network Address Translation)**. A router can translate private addresses into a public address when devices on the local network communicate with the internet.

### What I Practiced

I completed the TryHackMe **"What is Networking?"** room and used it to reinforce the networking concepts I learned today.

---

## Day 2: TCP/IP, Ports, Protocols, and How the Web Works

Today I continued from the networking basics and focused more on how devices actually communicate. I learned about TCP and UDP, common network ports, DNS, HTTP/HTTPS, and the basic process that happens when I open a website.

### TCP vs UDP

The main difference I learned is that TCP focuses on reliable delivery, while UDP focuses more on speed and lower overhead.

| | TCP | UDP |
|---|---|---|
| Reliable delivery | Yes | No |
| Speed | Generally slower | Generally faster |
| Handshake | Yes | No |
| Examples | HTTP, SSH, FTP, SMTP | DNS, streaming, VoIP, games |
| Best suited for | When accuracy matters | When speed matters more |

### The TCP 3-Way Handshake

I learned how a TCP connection is established using three steps:

1. **SYN:** The client asks to start a connection and sends a sequence number.
2. **SYN-ACK:** The server acknowledges the request and sends its own sequence number.
3. **ACK:** The client acknowledges the server, and the connection is established.

From a security perspective, this also helped me understand the idea behind a **SYN flood attack**. An attacker can send many SYN requests without completing the handshake, potentially exhausting the server's resources.

### Common Ports I Learned

| Port | Protocol | Transport | Main use / security point |
|---|---|---|---|
| 21 | FTP | TCP | File transfer; credentials can be sent without encryption |
| 22 | SSH | TCP | Secure remote access; commonly targeted by brute-force attacks |
| 23 | Telnet | TCP | Remote access without encryption |
| 25 | SMTP | TCP | Sending email |
| 53 | DNS | TCP/UDP | Domain name resolution |
| 80 | HTTP | TCP | Web traffic without TLS encryption |
| 110 | POP3 | TCP | Receiving email |
| 143 | IMAP | TCP | Receiving and managing email |
| 443 | HTTPS | TCP | Encrypted web traffic using TLS |
| 445 | SMB | TCP | Windows file and printer sharing |
| 1433 | MSSQL | TCP | Microsoft SQL Server |
| 3306 | MySQL | TCP | MySQL database connections |
| 3389 | RDP | TCP | Remote Desktop Protocol |
| 8080 | HTTP-Alt | TCP | Alternative HTTP port, often used by web applications |
| 9200 | Elasticsearch | TCP | Elasticsearch HTTP interface |

Learning common ports was useful because it gives me a better idea of what service might be running when I see a port during network enumeration.

### DNS: How a Domain Becomes an IP Address

I learned that when I type something like `google.com` into a browser, my computer does not directly know the server's IP address. It needs DNS to resolve the domain name.

The simplified process I learned is:

1. My computer asks a DNS resolver.
2. The resolver looks for the answer through the DNS hierarchy.
3. The root server points it toward the `.com` name servers.
4. The `.com` name servers point toward Google's authoritative name servers.
5. The authoritative server provides the IP address.
6. My browser can then connect to the returned IP address.

I also learned why DNS matters from a security perspective. **DNS poisoning** can cause a domain to resolve to an attacker's IP address instead of the legitimate one.

### HTTP vs HTTPS

I learned that HTTP normally uses port 80 and does not encrypt the connection, while HTTPS normally uses port 443 and protects the connection using TLS.

HTTPS is important for protecting information such as passwords while it is being transmitted, but it does not automatically make the website itself secure. Vulnerabilities such as SQL injection or XSS can still exist in an HTTPS application.

### How a Website Works

I also started connecting networking concepts to what happens when I visit a website. In a simplified example:

**Browser → HTTP request → Web server → Application code → Database → Web server → Browser**

The browser sends a request, the web server processes it, the application may communicate with a database, and the server sends the response back to the browser for rendering.

### Commands I Practiced

```bash
ipconfig              # View IP information on Windows
ping google.com       # Test connectivity
tracert google.com    # See the route packets take
nslookup google.com   # Resolve a domain to an IP address
netstat -an           # View network connections and listening ports
```

### What I Completed

- [x] TryHackMe: "What is Networking?"
- [x] TryHackMe: "DNS in Detail"
- [x] TryHackMe: "HTTP in Detail"
- [x] TryHackMe: "Networking Concepts"
- [x] TryHackMe: "Networking Core Protocols" theory
- [x] "How Websites Work" theory

---

## Next Step

My next goal is to continue building the fundamentals before moving deeper into cybersecurity tools and practical security work. I want these notes to grow with my progress, so future days will be added here as part of the same learning journey.

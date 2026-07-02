# Day 2 — TCP/IP, Ports & Protocols

## TCP vs UDP
| | TCP | UDP |
|---|---|---|
| Reliable | Yes | No |
| Speed | Slower | Faster |
| Handshake | Yes (3-way) | No |
| Examples | HTTP, SSH, FTP, SMTP | DNS, streaming, VoIP, games |
| Use when | Data accuracy matters | Speed matters more |

## The 3-way handshake
1. **SYN** — client says "I want to connect" + sends sequence number
2. **SYN-ACK** — server says "Got it, I'm ready too" + sends its own sequence number  
3. **ACK** — client says "Got it, let's go" — connection established

> Security note: A SYN flood attack sends millions of SYN packets without
> completing the handshake — fills the server's connection table until it crashes.

## Key ports cheatsheet
| Port | Protocol | TCP/UDP | Encrypted | Main security risk |
|------|----------|---------|-----------|-------------------|
| 21 | FTP | TCP | No | Plaintext creds, anonymous login |
| 22 | SSH | TCP | Yes | Brute force, stolen keys |
| 23 | Telnet | TCP | No | Everything plaintext — never use |
| 25 | SMTP | TCP | No | Open relay, email spoofing |
| 53 | DNS | TCP+UDP | No | Poisoning, tunneling, zone transfer |
| 80 | HTTP | TCP | No | SQLi, XSS, MITM, session hijack |
| 110 | POP3 | TCP | No | Credential sniffing |
| 143 | IMAP | TCP | No | Credential sniffing |
| 443 | HTTPS | TCP | Yes | SSL stripping, TLS downgrade |
| 445 | SMB | TCP | No | EternalBlue, WannaCry, Pass-the-Hash |
| 1433 | MSSQL | TCP | No | xp_cmdshell gives OS access |
| 3306 | MySQL | TCP | No | SQLi, data dump, UDF exploit |
| 3389 | RDP | TCP | Yes | BlueKeep, brute force, credential stuffing |
| 8080 | HTTP-Alt | TCP | No | Admin panels, default Tomcat creds |
| 9200 | Elasticsearch | TCP | No | No auth by default, full data dump |

## DNS — how it works
1. You type google.com in browser
2. Your computer asks the DNS resolver (usually your router)
3. Resolver asks the root nameserver
4. Root refers to .com nameserver
5. .com nameserver refers to Google's nameserver
6. Google's nameserver returns 142.250.80.46
7. Your browser connects to that IP

> Security risk: DNS poisoning injects a fake IP — you type bank.com
> but get sent to attacker's fake site instead.

## HTTP vs HTTPS
| | HTTP | HTTPS |
|---|---|---|
| Port | 80 | 443 |
| Encrypted | No | Yes (TLS) |
| Padlock | No | Yes |
| Safe for passwords | Never | Yes |

> Important: HTTPS encrypts the connection but NOT the application.
> SQL injection and XSS attacks still work on HTTPS sites.

## How websites work — summary
- Browser sends HTTP GET request to web server
- Web server runs code (PHP, Python, etc.)
- Code queries the database (MySQL port 3306)
- Database returns data
- Web server builds HTML and sends it back
- Browser renders the page

## Terminal commands practiced
```bash
ipconfig              # see your IP address (Windows)
ping google.com       # test connectivity
tracert google.com    # see route packets take (Windows)
nslookup google.com   # resolve domain to IP
netstat -an           # see all open ports and connections
```

## Private vs Public IP (from Day 1 bonus)
- Private: 192.168.x.x / 10.x.x.x / 172.16-31.x.x — inside your network only
- Public: assigned by ISP — visible on the internet
- NAT: router translates private → public IP when leaving your network

## Completed Labs
- [x] TryHackMe — "What is Networking?" room ✓
- [x] TryHackMe — "DNS in Detail" room ✓
- [x] TryHackMe — "HTTP in Detail" room ✓
- [x] TryHackMe — "Networking Concepts" room ✓
- [x] TryHackMe — "Networking Core Protocols" — covered in theory session ✓
- [x] "How Websites Work" — covered in theory session ✓
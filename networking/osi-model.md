# Day 1 -- OSI Model Notes

## The 7 Layers (top to bottom)

| Layer | Name         | Protocols                  | What it does                        |
|-------|--------------|----------------------------|-------------------------------------|
| 7     | Application  | HTTP, HTTPS, DNS, FTP, SSH | User-facing apps & services  |
| 6     | Presentation | SSL/TLS, JPEG              | Encryption, encoding, compression   |
| 5     | Session      | NetBIOS, RPC               | Opens and manages connections       |
| 4     | Transport    | TCP, UDP                   | Reliable delivery, port numbers     |
| 3     | Network      | IP, ICMP                   | Routing between networks, IP addrs  |
| 2     | Data Link    | Ethernet, ARP              | MAC addresses, same-network delivery|
| 1     | Physical     | Wi-Fi, cables              | Raw bits and signals                |

## Mnemonic
All People Seem To Need Data Processing (layers 7 → 1)

## Private vs Public IP (bonus)
- Private IPs: 192.168.x.x, 10.x.x.x, 172.16–31.x.x — only inside your network
- Public IP: assigned by ISP — visible on the internet
- NAT: your router translates private → public IP when traffic leaves your network

## Completed Labs
- [x] TryHackMe — "What is Networking?" room ✓
# Day 1: OSI Model and Networking Basics

Today I started with the OSI model. I learned that network communication can be understood through seven different layers, with each layer handling a different part of the communication process.

## The 7 Layers

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

## Private and Public IP Addresses

I also learned the difference between private and public IP addresses. Private IP addresses are used inside local networks, such as `192.168.x.x`, `10.x.x.x`, and `172.16.x.x` to `172.31.x.x`. A public IP address is assigned by an ISP and is used when communicating over the internet.

I also learned about **NAT (Network Address Translation)**. The router can translate private IP addresses into a public IP address when traffic leaves the local network.

## What I Practiced

I completed the TryHackMe **"What is Networking?"** room to practice the concepts I learned.

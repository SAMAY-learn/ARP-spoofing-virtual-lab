# ARP Spoofing Virtual Lab

## 📌 Project Overview
This project demonstrates an **ARP Spoofing (ARP Poisoning) attack** in a controlled **virtual lab environment** using **Kali Linux (attacker)** and **Ubuntu Linux (victim)**.  
The goal is to understand how attackers exploit the ARP protocol and how such attacks impact local networks.

⚠️ This project is strictly for **educational and ethical cybersecurity learning purposes only**.

---

## 🧠 What is ARP Spoofing?
ARP (Address Resolution Protocol) Spoofing is a **Man-in-the-Middle (MITM)** attack where an attacker sends fake ARP messages to associate their MAC address with the IP address of another device (usually the gateway).

This allows the attacker to:
- Intercept network traffic
- Monitor data packets
- Disrupt network communication

---

## 🧪 Lab Environment

| Role | Operating System |
|---|---|
| Attacker | Kali Linux |
| Victim | Ubuntu Linux |
| Virtualization | Oracle VirtualBox |
| Network Mode | Host-Only Adapter |
| DHCP | Enabled |

---

## ⚙️ Network Configuration
- Both VMs connected to **VirtualBox Host-Only Network**
- DHCP enabled for automatic IP assignment
- Internet access disabled (isolated lab)

---

## 🛠 Tools Used
- `arpspoof` (dsniff package)
- `ip` command
- `arp` command
- `sysctl`
- Oracle VirtualBox

---

## 🚀 Attack Procedure

### Step 1: Check IP Address
```bash
ip a
```
### Step 2: Check ARP Table
```bash
arp -a
```
### Step 3: Enable IP Forwarding (Attacker – Kali)
```bash
sudo sysctl -w net.ipv4.ip_forward=1
```
### Step 4: Perform ARP Spoofing
```bash
sudo arpspoof -i eth0 -t 192.168.56.4 192.168.56.1
```

# SOC-Project
# Homelab Cybersecurity SOC

## 📌 Project Overview
This project is a **Security Operations Center (SOC) homelab** that simulates a monitored network environment with **intrusion detection, SIEM, attack simulation, and incident response**. It is designed to provide hands-on experience with cybersecurity tools and methodologies.

## 🎯 Objectives
- Set up a virtualized SOC environment using **VirtualBox**.
- Implement a **Splunk SIEM** for log collection and analysis.
- Deploy **Suricata** as an **Intrusion Detection System (IDS)**.
- Configure **BIND DNS** for internal domain resolution.
- Perform **attack simulations** using a **Kali Linux VM**.
- Develop an **incident response workflow**.

---

## 🏗️ Lab Infrastructure

Each VM will have **two network interfaces**:
1. **NAT (eth0)** → Provides Internet access.
2. **Host-Only Network (eth1)** → Internal SOC communication.

| VM Name        | Role                  | Internal IP       | Domain Name           |
|---------------|----------------------|------------------|----------------------|
| Security VM   | Splunk SIEM + IDS     | 192.168.56.20    | splunk.soclab.oth    |
| Network VM    | BIND DNS + Syslog     | 192.168.56.10    | dns.soclab.oth       |
| Web Server    | Simulated Target      | 192.168.56.30    | web.soclab.oth       |
| Kali Linux    | Attack Simulation     | 192.168.56.40    | kali.soclab.oth      |

---

## 🖥️ Step-by-Step Setup

### 1️⃣ **Virtual Machine Configuration**
- Install **VirtualBox** and create VMs.
- Configure **Network Interfaces**:
  - NAT (Internet) → `eth0`
  - Host-Only (Internal) → `eth1`
- Set static IP addresses for each VM.

### 2️⃣ **Install and Configure BIND DNS (Network VM)**
- Install BIND9 (`sudo apt install bind9 -y`).
- Configure **forward and reverse DNS zones** (`/etc/bind/named.conf.local`).
- Set up **hostnames** for internal VMs.

### 3️⃣ **Install and Configure Splunk SIEM (Security VM)**
- Download Splunk `.deb` package.
- Install Splunk (`dpkg -i splunk.deb`).
- Enable and start the Splunk service.
- Configure log forwarding from other VMs.

### 4️⃣ **Deploy Suricata IDS (Security VM)**
- Install Suricata (`sudo apt install suricata -y`).
- Configure **Suricata** to monitor `eth1`.
- Enable **alert rules** for attack detection.

### 5️⃣ **Attack Simulation (Kali Linux VM)**
- Perform **Nmap scans, brute-force attacks, and exploit attempts**.
- Verify logs and alerts in **Splunk and Suricata**.

### 6️⃣ **Incident Response**
- Document attack detection results.
- Develop a basic **incident response plan**.
- Improve detection rules based on findings.

---

## 🔥 Tools Used
- **SIEM:** Splunk
- **IDS/IPS:** Suricata
- **DNS Server:** BIND9
- **Attack Simulation:** Kali Linux
- **Monitoring & Logging:** Syslog, Splunk Forwarders

---

## 📝 Future Enhancements
- Automate attack detection with **Sigma rules**.
- Implement **Wazuh** for endpoint monitoring.
- Use **MITRE ATT&CK** framework for threat mapping.
- Integrate **Grafana + Prometheus** for better visibility.

---

## 📚 Learning Outcomes
- Gain hands-on experience with **security tools**.
- Understand **SIEM, IDS, and monitoring concepts**.
- Learn how to **simulate and respond to attacks**.
- Build a **real-world cybersecurity homelab** for practice.

🚀 **This project is a great step toward a cybersecurity career!** Feel free to contribute or suggest improvements!


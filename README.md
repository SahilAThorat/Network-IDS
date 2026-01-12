# Network-IDS
🛡️ Network Intrusion Detection System (NIDS)
📌 Project Overview

This project implements a Network Intrusion Detection System (NIDS) to monitor network traffic, detect malicious activities, and generate alerts for security incidents. The system is designed to simulate an enterprise security monitoring environment similar to what is used in Security Operations Centers (SOC).

The NIDS uses Suricata/Snort to analyze network packets and detect threats such as port scans, brute-force attempts, malware communication, and suspicious network behavior.

🎯 Objectives

Monitor real-time network traffic

Detect common network attacks

Generate and analyze security alerts

Reduce false positives through rule tuning

Understand enterprise-level detection and response workflows

🏗️ Architecture
Attacker (Kali Linux)
        |
        |  Malicious Traffic
        v
Target System (Ubuntu / Windows)
        |
        |  Network Traffic
        v
NIDS Sensor (Suricata / Snort)
        |
        |  Alerts / Logs
        v
SIEM / Log Server (Elastic / Splunk / Wazuh)

🧰 Tools & Technologies

Suricata or Snort (NIDS Engine)

Kali Linux (Attack Simulation)

Ubuntu / Windows (Target Machine)

Elastic Stack / Splunk (Log Analysis - optional)

VirtualBox / VMware (Virtualization)

Wireshark (Traffic analysis)

🚨 Attack Scenarios Simulated
Attack Type	Tool Used	Purpose
Port Scanning	Nmap	Identify open ports
Brute Force	Hydra	Attempt unauthorized login
Malware Download	Metasploit / wget	Simulate malicious payload
Suspicious Traffic	Custom scripts	Trigger IDS rules
⚙️ Installation & Setup
1. Setup Virtual Machines

Kali Linux (Attacker)

Ubuntu (Victim)

Ubuntu (NIDS Sensor)

Ensure all VMs are on the same internal network.

2. Install Suricata
sudo apt update
sudo apt install suricata -y


Start Suricata:

sudo suricata -c /etc/suricata/suricata.yaml -i eth0

3. Test Detection

Run port scan from Kali:

nmap -sS <target-ip>


Check alerts:

sudo tail -f /var/log/suricata/fast.log

📊 Sample Output

Example alert:

[**] [1:2001219:3] ET SCAN Nmap Scripting Engine User-Agent Detected [**]

📁 Project Structure
NIDS-Project/
│
├── rules/               # Custom IDS rules
├── logs/                # Alert logs
├── reports/             # Incident reports
├── scripts/             # Attack simulation scripts
├── diagrams/            # Architecture diagrams
└── README.md

📝 Incident Response Workflow

Alert detected by NIDS

SOC analyst investigates source IP and behavior

Confirm malicious or false positive

Block IP / isolate host (simulated)

Document incident

🧪 Future Enhancements

Integrate with SIEM (Elastic / Splunk)

Add Machine Learning-based anomaly detection

Automate response using SOAR tools

Implement encrypted traffic analysis

📌 Learning Outcomes

Understanding of network protocols and attacks

Hands-on experience with IDS tools

Incident detection and investigation skills

Log analysis and reporting

Enterprise cybersecurity workflow simulation

📄 License

This project is for educational purposes only.

👤 Author
Sahil Thorat
Cybersecurity Enthusiast / Fresher

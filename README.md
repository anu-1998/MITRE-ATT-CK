# MITRE-ATT-CK

# 🛡️ Learning SOC Through Real Attacks – MITRE ATT&CK Journey

## 📌 Project Overview
This project represents my learning journey as a SOC analyst.

Instead of memorizing theory, I focused on understanding how real attacks happen in organizations — starting from phishing emails and ending in ransomware or data theft.

Each scenario in this project shows how a SOC analyst detects suspicious activity, maps it to the MITRE ATT&CK framework, understands the attack stage, and takes action to stop or contain the threat.

This is not a lab or simulation tool — it is a defender’s thinking project, built from a SOC point of view.

---

## 🧠 SOC Analyst Perspective
In a real SOC environment, alerts do not arrive labeled with MITRE technique IDs.  
They appear as suspicious emails, abnormal logins, unusual PowerShell executions, or unexpected network traffic.

The approach followed in this project is:
1. Understand what happened
2. Identify the attack stage
3. Map it to MITRE ATT&CK
4. Anticipate what could happen next
5. Respond early to minimize impact

---

## 🔥 Attack Scenarios Covered

### 1️⃣ Phishing – Initial Access
In this scenario, a user receives a fake email impersonating a trusted source such as Microsoft or internal HR. The email contains a malicious link or attachment designed to trick the user into interacting with it. From a SOC perspective, this activity is classified as Initial Access and mapped to MITRE ATT&CK technique T1566 (Phishing). The SOC’s goal at this stage is to detect and block the email before user interaction occurs.

Real life:
A user receives a fake email impersonating Microsoft or HR.

MITRE Tactic: Initial Access

Technique: T1566 – Phishing

Kill Chain Stage: Delivery

SOC Detection:

SPF / DKIM / DMARC failures

Suspicious sender domain

Email gateway alerts

SOC Goal:
🚫 Block email before user interaction

---

### 2️⃣ Malicious Execution – PowerShell or Script
After a user interacts with a phishing email, malicious code may execute on the endpoint through PowerShell or a downloaded executable. This activity maps to the Execution tactic, specifically T1059 (Command and Scripting Interpreter). SOC analysts monitor endpoint behavior, suspicious command-line activity, and EDR alerts. Early detection here helps prevent persistence and further compromise.

Real life:
User clicks link → PowerShell script runs silently.

MITRE Tactic: Execution

Technique: T1059.001 – PowerShell

Kill Chain Stage: Exploitation / Execution

SOC Detection:

Suspicious PowerShell commands

Unsigned scripts

External connections

SOC Goal:
🛑 Stop execution before persistence or credential theft
---

### 3️⃣ Credential Access – LSASS Memory Dumping
Once execution is successful, attackers often attempt to steal credentials to expand their access. This is commonly done by dumping credentials from LSASS memory and is mapped to T1003.001 (LSASS Memory). From a SOC point of view, this is a critical alert because compromised credentials can quickly lead to widespread access. Immediate containment and credential resets are required.

Real life:
Attacker steals passwords from memory.

MITRE Tactic: Credential Access

Technique: T1003.001 – LSASS Memory

SOC Detection:

EDR alerts on LSASS access

Mimikatz indicators

Unusual admin activity

SOC Goal:
🔒 Disable compromised accounts immediately
---

### 4️⃣ Lateral Movement – Remote Services
Using stolen credentials, attackers move laterally across the network using remote services such as RDP or SMB. This behavior is mapped to the Lateral Movement tactic using T1021 (Remote Services). SOC teams detect this by analyzing login logs, abnormal access patterns, and privileged account usage. Preventing lateral movement is key to stopping large-scale attacks like ransomware.

Real life:
Attacker moves from one system to another.

MITRE Tactic: Lateral Movement

Technique: T1021 – Remote Services

RDP, SMB, WinRM

SOC Detection:

Abnormal login patterns

Windows Event ID 4624

Logon type 10 (RDP), 3 (SMB)

SOC Goal:
🧱 Stop attacker from spreading
---

### 5️⃣ Collection – Data Gathering
After accessing critical systems, attackers begin collecting sensitive data such as files, databases, or email archives. This activity falls under the Collection tactic and maps to techniques such as T1005 (Data from Local System) and T1039 (Data from Network Share). SOC analysts look for abnormal file access, data staging, and compression activity. Detecting this stage can stop a breach before data leaves the organization.

Real life:
Attacker searches file servers and databases.

MITRE Tactic: Collection

Techniques:

T1005 – Data from Local System

T1039 – Data from Network Share

SOC Detection:

Unusual file access

Data compression (ZIP/RAR)

Access by non-normal users

SOC Goal:
⏱️ Stop before exfiltration
---

### 6️⃣ Command and Control – Application Layer Protocols
To maintain control over infected systems, attackers establish communication with their infrastructure using common protocols like HTTP, HTTPS, or DNS. This behavior maps to T1071 (Application Layer Protocol). From a SOC perspective, this traffic often blends with legitimate network traffic, making behavioral analysis essential. Detecting beaconing patterns or suspicious domains allows SOC teams to disrupt attacker control.

6️⃣ Command & Control – Application Layer Protocols

Real life:
Malware communicates with attacker server.

MITRE Tactic: Command and Control

Technique: T1071 – Application Layer Protocol

HTTP / HTTPS / DNS

SOC Detection:

Beaconing behavior

Rare domains

Suspicious encrypted traffic

SOC Goal:
🔌 Cut communication with attacker infrastructure
---

### 7️⃣ Exfiltration – Data Leaving the Network
Once data is collected, attackers attempt to exfiltrate it outside the organization. This activity maps to the Exfiltration tactic, commonly T1041 (Exfiltration over Command and Control Channel). SOC analysts monitor outbound traffic for unusual data transfers, unknown destinations, and protocol misuse. Preventing exfiltration can significantly reduce the impact of an incident.

Real life:
Sensitive data is sent outside the organization.

MITRE Tactic: Exfiltration

Technique: T1041 – Exfiltration over C2 Channel

SOC Detection:

Large outbound data transfers

Uploads to unknown destinations

SOC Goal:
🚨 Prevent data breach
---

### 8️⃣ Impact – Ransomware or Data Destruction
In the final stage, attackers may encrypt files, disrupt services, or destroy data to cause maximum damage. This behavior is mapped to T1486 (Data Encrypted for Impact). SOC detection focuses on mass file modifications, abnormal system behavior, and ransom indicators. The priority at this stage is containment, recovery, and incident response coordination.

Real life:
Files are encrypted, systems unavailable.

MITRE Tactic: Impact

Technique: T1486 – Data Encrypted for Impact

SOC Detection:

Mass file encryption

Ransom notes

CPU/Disk spikes

SOC Goal:
🛡️ Contain, recover, and report
---

## 🧭 Frameworks Used
- MITRE ATT&CK Framework
- Cyber Kill Chain
- SOC Detection & Response Methodology

---

## 🎯 Key Skills Demonstrated
- SOC alert analysis
- MITRE ATT&CK mapping
- Kill chain understanding
- Incident response thinking
- Clear security documentation

---

## ⚠️ Disclaimer
This project is for educational and defensive purposes only.  
All scenarios are based on publicly known attack patterns and common SOC use cases.  
No real malware, exploits, or sensitive data are included.

---



## ✅ Final Note
This project reflects how a SOC analyst thinks and responds to real-world threats, focusing on early detection, proper classification, and effective response using the MITRE ATT&CK framework.

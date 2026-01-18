MITRE ATT&CK – SOC Attack Scenario Mapping

This repository demonstrates a practical attack scenario mapped to the MITRE ATT&CK framework using the MITRE ATT&CK Navigator.
The project is designed to showcase how a SOC analyst can model and understand real-world attacker behavior from initial access to data exfiltration.

📌 Project Overview

The goal of this project is to:

Practice mapping attack techniques to MITRE ATT&CK

Visualize attack flow using ATT&CK Navigator

Understand how attackers move through different tactics during an intrusion

Build SOC-focused documentation suitable for learning and portfolio purposes

This is a practice / learning project, not a full APT simulation.

🧨 Attack Scenario Summary

The simulated attack follows this flow:

Phishing email with a malicious Excel attachment

User enables macros, triggering PowerShell execution

PowerShell downloads and executes a payload in memory

Persistence established using Registry Run keys

Credentials dumped from LSASS

Lateral movement using RDP

Sensitive data exfiltrated over HTTPS to a C2 server

# 🛡️ Detecting Password Spray Activity with Wazuh in an Active Directory Lab

## Overview

This project shows how I built a small home SOC-style lab using Wazuh to monitor a Windows Active Directory environment. The goal was to deploy a working Wazuh server, connect Windows systems as agents, and prepare the lab for detecting suspicious authentication activity like password spraying.

## 🎯 Objective

In this lab, I wanted to:

* deploy Wazuh in a home lab
* connect Windows endpoints to the dashboard
* verify connectivity and agent status
* build a foundation for future password spray detection

## 🖥️ Lab Environment

### Virtual Machines

* **Wazuh-Server** — Ubuntu Server 24.04.4 LTS
* **dc01** — Windows Server domain controller
* **win10-lab** — Windows 10 endpoint
* **Kali** — attacker workstation
* **Metasploitable** — vulnerable target VM

### Network Setup

* **Host-only** for internal lab communication
* **NAT** for internet access, updates, and package downloads

## ⚙️ What I Built

I installed Wazuh on a dedicated Ubuntu Server VM and deployed the Wazuh agent to:

* **win10-lab**
* **dc01**

Both systems successfully connected back to the Wazuh server and showed as active in the dashboard.

## ✅ Results

This lab successfully demonstrated:

* Wazuh server deployment in a virtual lab
* onboarding a Windows 10 endpoint and domain controller
* validating connectivity between agents and the manager
* troubleshooting networking, DNS, and install issues

At the end of the lab, these agents were active:

* **win10-lab**
* **dc01**

## 🛠️ Challenges I Solved

A few issues came up during the setup:

* **Metasploitable was 32-bit**, so I used a new Ubuntu Server VM for Wazuh
* **network adapters** had to be corrected for host-only and NAT access
* **Ubuntu networking** required netplan changes
* **Windows DNS** issues had to be fixed before agent downloads worked
* **Windows Server** initially failed because the MSI was not copied over yet

## 🧠 Skills Demonstrated

This project helped me practice:

* SIEM deployment
* endpoint onboarding
* Windows and Ubuntu administration
* VirtualBox networking
* DNS and connectivity troubleshooting
* documenting a security lab for GitHub

## 🧭 MITRE ATT&CK

This lab supports future detection work related to:

* **T1110.003 — Password Spraying**

## 📸 Screenshots Included

This repo includes screenshots of:

* the Wazuh dashboard
* active agents
* Wazuh server networking
* Windows 10 and Windows Server agent status
* endpoint connectivity to the Wazuh server

## 📚 What I Learned

This lab showed me that building the monitoring environment takes more than just installing software. Most of the work involved troubleshooting networking, DNS, operating system compatibility, and endpoint communication.

It also showed the value of using a dedicated monitoring server instead of trying to force multiple roles onto one system.

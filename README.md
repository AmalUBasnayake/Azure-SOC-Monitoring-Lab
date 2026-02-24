# 🛡️ Azure SOC Monitoring & Incident Alerting Lab
<p align="center">

![Azure](https://img.shields.io/badge/Platform-Microsoft%20Azure-0078D4?style=for-the-badge&logo=microsoftazure&logoColor=white)
![Security](https://img.shields.io/badge/Focus-Cloud%20Security-8A2BE2?style=for-the-badge)
![Architecture](https://img.shields.io/badge/Model-Zero%20Trust-red?style=for-the-badge)
![Status](https://img.shields.io/badge/Deployment-Successful-brightgreen?style=for-the-badge)

</p>


## 📌 Project Overview
In this hands-on lab, I established a cloud-based security monitoring system using **Microsoft Azure**. The primary objective was to simulate a Security Operations Center (SOC) workflow by configuring real-time alerts for critical system events. 

I successfully configured an alerting mechanism that monitors for **Virtual Machine restarts**, ensuring that any potential unauthorized access or system instability is instantly reported to a security analyst.

---

## 🏛️ Architecture Overview

The monitoring pipeline follows a structured flow to ensure zero-latency incident detection, as illustrated below:

1. **Event Source:** An administrative action (e.g., VM Restart) occurs on the **Victim-VM**.
2. **Logging:** The event is captured and stored in the **Azure Activity Log**.
3. **Detection:** **Azure Monitor** continuously evaluates the Activity Log against a pre-defined **Alert Rule** for specific signals.
4. **Action:** Upon a positive match of the alert condition, the configured **Action Group** is triggered.
5. **Notification:** The Action Group executes the configured action, dispatching a real-time notification to the **Security Analyst's Email**.

![Azure Monitoring Architecture Diagram](./screenshots/architecture-diagram.png)

---

## 🛠️ Tech Stack & Tools
* **Cloud Platform:** Microsoft Azure
* **Monitoring:** Azure Monitor & Activity Logs
* **Automation:** Azure Action Groups
* **Target System:** Ubuntu Linux Virtual Machine

---

## 🚀 Implementation & Configuration

### 1. Alert Rule Logic
I defined a custom signal logic to detect whenever the `Microsoft.Compute/virtualMachines/restart/action` event occurs.
![Alert Rule Setup](./screenshots/alertrule.png)

### 2. Action Group & Notification
Configured an Action Group to automate the notification process via email.
![Action Group Configuration](./screenshots/Actiongroup.png)

---

## 📊 Lab Results

### ✅ Incident Dashboard
The Azure Monitor dashboard successfully captured multiple alert instances following the manual triggers.
![Azure Monitor Dashboard](./screenshots/Aleartdash.png)

### ✅ Real-time Email Proof
This is the automated email alert received immediately after the incident was detected.
![Email Alert Notification](./screenshots/emailproof.png)

---

## 🛡️ Security Significance
* **Visibility:** 24/7 monitoring of critical infrastructure changes.
* **MTTD:** Significantly reduces the Mean Time to Detect incidents.
* **Compliance:** Maintains a clear audit trail for security investigations.

---

## 📝 Conclusion
This lab demonstrates how to leverage cloud-native tools to build a proactive security monitoring solution, a vital skill for any SOC Analyst or Cloud Security Engineer.


---
**Author:** Amal Udayanga Basnayake

**LinkedIn:** https://www.linkedin.com/in/amal-udayanga-basnayake/

**GitHub:** https://github.com/AmalUBasnayake

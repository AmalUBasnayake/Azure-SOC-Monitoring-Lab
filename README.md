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
  * **Monitoring Services:** Azure Monitor & Activity Logs
  * **Automation:** Azure Action Groups (for Notification Services)
  * **Target System:** Ubuntu Linux Virtual Machine

---

## 🚀 Implementation Steps

### 1\. Action Group Setup

An **Action Group** named `Email-Alerts` was created. This serves as the notification backbone, mapping specific security personnel to incident types via email.

### 2\. Alert Rule Configuration

A custom **Alert Rule** was configured within Azure Monitor, targeting the Azure Activity Log:

  * **Signal Name:** `Restart Virtual Machine (Microsoft.Compute/virtualMachines/restart/action)`
  * **Logic:** The alert triggers whenever an administrative "Restart Virtual Machine" event successfully occurs.

### 3\. Incident Validation

To test the end-to-end functionality, a manual restart was performed on the `Victim-VM`. This action simulated a real-world incident and validated the effectiveness of the monitoring setup.

---

## 📊 Lab Results

### ✅ Incident Dashboard

The Azure Monitor dashboard successfully captured and displayed multiple alert incidents, confirming the system's operational status.

### ✅ Real-time Email Notification

The system promptly dispatched a high-priority email notification to the configured security analyst's inbox, demonstrating successful incident communication.

---

## 🛡️ Security Significance

  * **Enhanced Visibility:** Provides continuous, 24/7 visibility into critical resource lifecycle events.
  * **Rapid Incident Response:** Significantly reduces **Mean Time to Detect (MTTD)** by automating alerts.
  * **Auditability & Forensics:** Creates an immutable audit trail within Activity Logs for post-incident analysis.

---

## 📝 Conclusion

This project stands as a practical demonstration of implementing **Cloud Security Posture Management (CSPM)**. Establishing robust, automated monitoring and alerting systems is a cornerstone for maintaining a strong security posture in dynamic cloud environments.

---
**Author:** [Your Name]
**LinkedIn:** [Your LinkedIn Profile Link]
**GitHub:** [Link to this GitHub Repo]

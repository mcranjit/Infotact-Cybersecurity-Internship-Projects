# ✅ Project 3 Checklist – Secure Linux Server Setup & Hardening

**Internship**: Infotact Solutions  
**Role**: Security Admin Associate – L1  
**Mentor**: Vasudev Jha  
**Project Title**: Secure Linux Server Setup & Hardening  
**Operating System**: Ubuntu Server 22.04 LTS  
**Objective**: Deploy and harden a Linux server with enterprise-grade security controls.

---

## 🖥️ 1. Server Deployment

- [x] Deployed Ubuntu Server (Locally or on Cloud)
- [x] Created a new user with sudo privileges
- [x] Updated and upgraded the system  
  `sudo apt update && sudo apt upgrade -y`

---

## 🔐 2. SSH Configuration

- [x] Disabled root login  
  In `/etc/ssh/sshd_config`:  
  `PermitRootLogin no`
- [x] Disabled password-based login  
  `PasswordAuthentication no`
- [x] Enforced SSH key authentication
- [x] Restarted SSH service  
  `sudo systemctl restart sshd`

---

## 🔥 3. Firewall (UFW) Configuration

- [x] Installed UFW  
  `sudo apt install ufw`
- [x] Allowed essential ports (SSH, HTTP, HTTPS)  
  ```bash
  sudo ufw allow 22/tcp
  sudo ufw allow 80/tcp
  sudo ufw allow 443/tcp

* [x] Denied all other unnecessary ports
* [x] Enabled firewall
  `sudo ufw enable`
* [x] Checked status
  `sudo ufw status verbose`

---

## 🛡️ 4. Intrusion Protection with Fail2Ban

* [x] Installed Fail2Ban
  `sudo apt install fail2ban`
* [x] Configured jail settings in `jail.local`
* [x] Enabled and started Fail2Ban
  `sudo systemctl enable --now fail2ban`
* [x] Verified jail status
  `sudo fail2ban-client status`

---

## 📋 5. System Auditing with auditd

* [x] Installed auditd
  `sudo apt install auditd`
* [x] Enabled and started auditd
  `sudo systemctl enable --now auditd`
* [x] Verified logging of user and system events
  `sudo ausearch -x sshd`

---

## 🧪 6. Vulnerability Scanning

* [x] Performed scan from Kali Linux
  `nmap -sV -A <server IP>`
* [x] Analyzed open ports and services
* [x] Removed or hardened unnecessary services
* [x] Re-verified with follow-up scans

---

## 📄 7. Documentation & Reporting

* [x] Saved all command outputs and screenshots
* [x] Documented step-by-step configurations
* [x] Prepared detailed final report (PDF)
* [x] Recorded a video demonstration
* [x] Uploaded files to GitHub

---

## 🛠️ Final Remediation Checklist

| Security Gap              | Action Taken / Recommendation                  |
| ------------------------- | ---------------------------------------------- |
| Root SSH login enabled    | Disabled via SSH config                        |
| Weak login methods        | Enforced key-based SSH login                   |
| Unused ports open         | Blocked with UFW                               |
| Brute-force vulnerability | Installed and configured Fail2Ban              |
| Lack of audit trail       | Enabled auditd for monitoring                  |
| Unpatched packages        | Regularly update using `apt update && upgrade` |

---

📌 **System Status**: ✅ Hardened and Compliant
📅 **Last Updated**: August 7, 2025

---

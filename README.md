# publisher-linux-remediation
Security remediation on a vulnerable Publisher Linux machine including SSH hardening, HTTPS configuration, SPIP CMS update, and brute-force protection using Fail2Ban.
# Remediating Publisher (Linux Machine)

## 🔐 Overview
This project presents the remediation phase for a previously exploited Linux-based virtual machine named **Publisher**. The system was hardened to close critical vulnerabilities, configure secure protocols, update exposed services, and implement brute-force mitigation mechanisms.

## 🛠️ Key Remediations Performed

### 1. SSH Hardening
- Created a new sudo user `newuser1` with restricted SSH access.
- Configured `/etc/ssh/sshd_config` to allow access only from a trusted IP (`192.168.1.106`).
- Denied SSH access from unauthorized machines (e.g., Windows client).

### 2. Secure SSH Key Permissions
- Identified over-permissive private key (`id_rsa`) file for user `think`.
- Set strict file permissions to restrict access (`chmod 600`).

### 3. Enforced HTTPS (Port 443)
- Generated a self-signed SSL certificate.
- Enabled SSL modules and Apache's `default-ssl.conf`.
- Configured automatic HTTP to HTTPS redirection.
- Set `ServerName` in Apache configuration for proper SSL resolution.
- **Note**: SSL warning due to certificate mismatch persisted, despite reconfiguration.

### 4. SPIP CMS Upgrade
- Used `spip_loader.php` to upgrade SPIP from vulnerable version to **v4.3.1**.
- Verified the version upgrade using **WhatWeb** and browser access.
- Setup fresh SPIP database and admin account as part of secure deployment.

### 5. Brute-force Mitigation
- Installed and configured **Fail2Ban**.
- Set `maxretry = 100` to block excessive login attempts on SSH.

## 📄 Report Included
- `Remediating Publisher (Linux Machine).pdf`: Step-by-step screenshots and explanations of each mitigation technique.

## 📌 Disclaimer
This project was conducted in a virtual lab setup for academic learning purposes only. All remediations were performed ethically on intentionally vulnerable systems.

---

> 🧑‍💻 *Performed by Mohammad Kaif as part of system hardening practice in cybersecurity labs.*

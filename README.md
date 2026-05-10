# Firewall-UFW

A professional bash automation script to install, configure, and harden your network security on Arch Linux using UFW (Uncomplicated Firewall).

## 📌 Overview

This script is designed to streamline the initial security setup of an Arch-based system. It moves away from an "open-by-default" configuration to a "Secure-by-Default" stance, ensuring that your system is protected immediately after installation.

## 🚀 Security Policy & Hardening

- **Default Inbound Policy:** `DENY` (All unsolicited incoming traffic is blocked).
- **Default Outbound Policy:** `ALLOW` (System updates and user traffic are permitted).
- **SSH Rate Limiting:** Uses `limit 22` instead of a simple allow. This provides a basic layer of defense against SSH brute-force attacks by limiting connection attempts.
- **Service Persistence:** Fully integrates with `systemd` to ensure the firewall remains active across reboots.

## 🛠️ Usage

  **Clone the repository:**
   ```bash
   git clone [https://github.com/yourusername/firewall-ufw.git](https://github.com/yourusername/firewall-ufw.git)
   cd firewall-ufw
   Grant execution permissions:
   chmod +x firewall-ufw.sh

   **Execute with administrative privileges:**
   sudo ./firewall-ufw.sh

📝 Script Logic

The script follows a logical security workflow:

    Environment Check: Targeted for Arch-based distributions using pacman.

    Installation: Deploys the UFW package.

    Rule Application: Configures global policies and specific port protections.

    Daemon Activation: Starts and enables the firewall services via systemctl.

    Audit: Outputs the current status to verify all rules are correctly applied.

⚠️ Requirements

    Package Manager: pacman

    Privileges: sudo access is mandatory for network and package modifications.




# Arch-Log-Auditor

A lightweight system utility designed to parse and analyze the Pacman package manager logs on Arch-based distributions.

## 📌 Overview
Monitoring system changes is a critical part of security and system administration. This tool provides a quick way to audit recent package installations, allowing administrators to verify system modifications and track potential unauthorized software additions.

## 🚀 Features
- **Flexible Auditing:** Allows the user to specify exactly how many recent events to retrieve.
- **Direct Log Parsing:** Accesses `/var/log/pacman.log` directly for high-speed analysis.
- **Traceability:** Helps in troubleshooting system instability by identifying the most recent changes to the OS.

## 🛠️ Usage
1. **Ensure you have read permissions** for `/var/log/pacman.log`.
2. **Make it executable:**
   ```bash
   chmod +x log-audit.sh
Run the tool:
    Bash

    ./log-audit.sh


## 📝 Script Logic
The script uses a combination of `grep` and `tail`:
- `grep "installed"`: Filters the log file to show only successful installation events, ignoring removals or updates.
- `tail -n [X]`: Limits the output to the most recent 'X' entries provided by the user.

## ⚠️ Requirements
- **OS:** Arch Linux or any Pacman-based distribution (Manjaro, EndeavourOS).
- **Files:** Access to `/var/log/pacman.log`.

---
*Developed for system integrity monitoring and administrative transparency.*

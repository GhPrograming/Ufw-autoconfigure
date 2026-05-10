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

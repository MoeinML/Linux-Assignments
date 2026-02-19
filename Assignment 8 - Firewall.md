# Assignment 8: Server Firewall Configuration

## Introduction
A firewall is a security system that monitors and controls incoming and outgoing network traffic based on predetermined security rules. It acts as a barrier between a trusted network and untrusted networks (like the internet). 

The goal of this exercise is to protect our server by:
* Allowing only necessary services (SSH, HTTP, HTTPS).
* Blocking unauthorized access.
* Preventing common network attacks like SYN flooding.

## Implementation Roadmap

To configure the firewall correctly without losing access to the server, I will follow these steps:

1.  **Prerequisites:** Install `ufw` and `fail2ban`.
2.  **Access Rules:** Configure SSH limits to prevent lockout and Brute Force attacks.
3.  **Service Rules:** Allow standard web traffic (Port 80 and 443).
4.  **Security Hardening:** Enable logging and set up protection against SYN Flood attacks.
5.  **Automation:** Enable Fail2Ban to monitor logs and ban malicious IPs automatically.

## Step 1: Installing Prerequisites
To build a secure firewall, I first need to install the necessary tools: **UFW** and **Fail2Ban**.

* `sudo apt update`: Updates the package list to ensure I install the latest versions.
* `sudo apt install ufw fail2ban -y`: Installs the Uncomplicated Firewall (UFW) and the Fail2Ban intrusion prevention service.

**Why:** UFW is used for defining network rules, and Fail2Ban is used to automatically block malicious IP addresses that show suspicious behavior (like too many failed login attempts).

### Verification of Installation
After installation, I verified that Fail2Ban is active and running to ensure the intrusion prevention system is ready.

* `sudo systemctl status fail2ban`: This command confirms the service status.

![Installation Status](Images/AS8-1.jpg)

## Step 2: Configuring SSH Access
* `sudo ufw limit ssh`: This rule allows SSH access (Port 22) but adds protection by limiting the number of connections from a single IP. 

**Why:** If an IP tries to connect too many times in a short period (like a Brute Force attack), UFW will block it. This ensures I don't get locked out and protects the server from password-guessing bots.

![AS8-2.jpg](Images/AS8-2.jpg)

## Step 3: Allowing Web Traffic
To allow the server to function as a web server, I need to open the standard ports for web traffic.

* `sudo ufw allow http`: This opens port 80, which is the default port for unencrypted web traffic.
* `sudo ufw allow https`: This opens port 443, which is the default port for secure (encrypted) web traffic.

**Why:** Without these rules, the firewall would block any attempt to visit a website or web service hosted on this server. Opening only these specific ports follows the security principle of "least privilege" (only opening what is strictly necessary).

![AS8-3.jpg](Images/AS8-3.jpg)



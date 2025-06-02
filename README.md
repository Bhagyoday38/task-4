# task-4

# 🔥 UFW Firewall Configuration and Testing on Ubuntu

## 📋 Objective

To configure and test basic firewall rules using **UFW (Uncomplicated Firewall)** on a Debian-based Linux system. Focus is on allowing **SSH (port 22)** and blocking **Telnet (port 23)** traffic.

---

## 🛠️ System Configuration and Tools

- **Operating System:** Ubuntu / Debian-based Linux
- **Firewall Tool:** UFW (Uncomplicated Firewall)
- **Terminal Access:** Required (CLI operations)
- **Testing Tool:** `telnet` (to verify port accessibility)

---

## 🔧 Steps, Commands, and Observations

### 1. Update Package List
```bash
sudo apt update
Purpose: Ensures latest package info for installing UFW.

2. Install UFW
bash

sudo apt install ufw
Purpose: Installs UFW if not already present.

3. Allow SSH Traffic (Port 22)
bash

sudo ufw allow 22/tcp
Purpose: Prevents lockout, especially for remote access.

4. Enable UFW
bash

sudo ufw enable
Expected Output:

pgsql

Command may disrupt existing ssh connections. Proceed with operation (y|n)? y
Firewall is active and enabled on system startup
5. View Current Firewall Rules
bash

sudo ufw status verbose
Purpose: Displays current active firewall rules with details.

6. Block Telnet (Port 23)
bash

sudo ufw deny 23/tcp
Purpose: Blocks inbound Telnet traffic to demonstrate port filtering.

7. Test Rule with Telnet
bash

telnet localhost 23
Expected Output:

vbnet

Trying 127.0.0.1...
telnet: Unable to connect to remote host: Connection refused
Purpose: Confirms Telnet port is successfully blocked.

8. (Re)Allow SSH Access (Optional)
bash
Copy
Edit
sudo ufw allow 22/tcp
Purpose: Ensures SSH remains allowed post-changes.

9. Remove the Block Rule on Port 23
bash

sudo ufw delete deny 23/tcp
Expected Output:

mathematica

Rule deleted
Rule deleted (v6)
Purpose: Cleans up test rule to restore default state.

📌 Summary of Firewall Behavior
UFW simplifies firewall rule management on Linux.

Allows and denies inbound traffic with simple commands.

SSH (port 22) was allowed for remote access.

Telnet (port 23) was blocked and verified via testing.

Block rule was deleted after testing to reset firewall.

UFW rules are persistent across reboots unless manually modified.

✅ Conclusion
We successfully configured a basic firewall using UFW, tested traffic filtering rules, and verified their effectiveness. This foundation can be extended to implement robust security policies on servers and desktops alike.

📎 Additional Tips
Use sudo ufw status numbered to list rules with index numbers.

Use sudo ufw delete <number> to remove specific rules.

Use sudo ufw disable to temporarily disable UFW.


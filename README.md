# Elevate Labs Cyber Security Internship - Task 4

## 🎯 Task: Setup and Use a Firewall on Linux
### 📝 Objective
The objective of this task is to configure and test basic firewall rules to allow or block network traffic using UFW (Uncomplicated Firewall) on Linux.

---

### 🛠️ Execution & Commands Used
The following steps were executed in the Linux terminal to manage firewall rules:

1. **Check and Enable Firewall:**
   Started the UFW firewall to begin traffic filtering.
   * `sudo ufw status`
   * `sudo ufw enable`

2. **Block Inbound Traffic (Telnet):**
   Added a rule to block port 23, which is used by the insecure Telnet protocol.
   * `sudo ufw deny 23/tcp`

3. **Allow Secure Traffic (SSH):**
   Added a rule to explicitly allow SSH connections on port 22 for secure remote management.
   * `sudo ufw allow 22/tcp`

4. **Verify Applied Rules:**
   Checked the active rules to confirm the changes.
   * `sudo ufw status verbose`

5. **Test the Block Rule:**
   Attempted to connect to the blocked port locally to verify traffic is dropped.
   * `telnet localhost` (Result: Connection refused/Timeout)

6. **Cleanup (Restore Original State):**
   Removed the temporary block rule after testing.
   * `sudo ufw delete deny 23/tcp`

---

### 🚦 Summary: How a Firewall Filters Traffic
A firewall acts as a digital security guard between a computer and the network. It filters traffic by inspecting the headers of incoming (inbound) and outgoing (outbound) data packets. It checks parameters like the source IP address, destination IP, and specific ports (e.g., Port 22 or 23) against a predefined set of rules (Allow or Deny). If the packet matches a "Deny" rule, it is dropped; if it matches an "Allow" rule, it passes through.

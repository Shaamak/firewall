

## ⚖️ Objective
To configure a firewall, manage traffic rules, test its behavior, and restore the system to its original state. This was done on a **Linux** system using **UFW (Uncomplicated Firewall)**.

---

## 🔧 Steps Performed

### 1. Opened Firewall Configuration Tool
```bash
sudo ufw status
```
If UFW is inactive:
```bash
sudo ufw enable
```

---

### 2. Listed Current Firewall Rules
```bash
sudo ufw status verbose
```

---

### 3. Added Rule to Block Inbound Port 23 (Telnet)
```bash
sudo ufw deny 23
```

---

### 4. Tested Block Rule
Attempted to connect to port 23 locally using:
```bash
telnet localhost 23
```
Confirmed that the connection was refused or timed out, proving the rule was effective.

---

### 5. Allowed SSH (Port 22)
```bash
sudo ufw allow 22
```

---

### 6. Removed Test Block Rule
```bash
sudo ufw delete deny 23
```

---

## 📝 Summary of Commands
```bash
sudo ufw enable
sudo ufw status verbose
sudo ufw deny 23
sudo ufw allow 22
sudo ufw delete deny 23
```

---

## 🚀 How Firewall Filters Traffic (Brief Summary)
- UFW acts as a wrapper around `iptables`, managing rules more easily.
- It filters traffic based on:
  - Port number
  - Direction (inbound or outbound)
  - Protocol (TCP/UDP)
- Only explicitly allowed connections are accepted; everything else is denied by default when configured.


```

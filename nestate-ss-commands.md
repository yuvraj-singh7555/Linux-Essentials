# Network Monitoring with `netstat` and `ss` Commands

Welcome to the **Network Monitoring Guide**! This repository provides an in-depth explanation of `netstat` and `ss` commands used for monitoring active connections, listening ports, and overall network statistics. 
---

###  RHEL/CentOS:
##  Installation (If Not Available)

```bash
sudo yum install net-tools
```

###  Debian/Ubuntu:
```bash
sudo apt install net-tools
```

For `ss` command, install `iproute2`:
```bash
sudo apt install iproute2
```

---
Here is a **comprehensive list** of `netstat` and `ss` commands along with their descriptions:

---

## 🛠 **Netstat Commands List** (`net-tools`)

| Command | Description |
|---------|------------|
| `netstat` | Show all active connections. |
| `netstat -a` | Show all listening and non-listening (active) connections. |
| `netstat -t` | Show only TCP connections. |
| `netstat -u` | Show only UDP connections. |
| `netstat -l` | Display only listening connections. |
| `netstat -n` | Show numerical addresses instead of resolving hostnames. |
| `netstat -p` | Show the process using the connection (with PID). |
| `netstat -r` | Display the kernel routing table. |
| `netstat -i` | Show statistics for network interfaces. |
| `netstat -s` | Show detailed network statistics. |
| `netstat -g` | Display multicast group membership. |
| `netstat -c` | Continuously print network statistics (every second). |
| `netstat -M` | Display network masquerading connections. |
| `netstat -e` | Show extended information about connections. |
| `netstat -o` | Show connection timers. |
| `netstat -lt` | Show listening TCP ports. |
| `netstat -lu` | Show listening UDP ports. |
| `netstat -tun` | Show TCP and UDP connections in numeric format. |
| `netstat -anp` | Show all active connections with process names. |

---

##  **SS (Socket Statistics) Commands List** (`iproute2`)

| Command | Description |
|---------|------------|
| `ss` | Show all active sockets. |
| `ss -l` | Show only listening sockets. |
| `ss -t` | Display TCP connections. |
| `ss -u` | Display UDP connections. |
| `ss -w` | Display RAW socket connections. |
| `ss -x` | Display UNIX domain socket connections. |
| `ss -p` | Show process name (PID) using the connection. |
| `ss -r` | Resolve hostnames for IP addresses. |
| `ss -s` | Show summary statistics of socket usage. |
| `ss -n` | Show numerical addresses without resolving hostnames. |
| `ss -o` | Display socket timers. |
| `ss -m` | Show memory usage of sockets. |
| `ss -i` | Display internal TCP information. |
| `ss -4` | Show only IPv4 sockets. |
| `ss -6` | Show only IPv6 sockets. |
| `ss -tuln` | Show TCP and UDP listening ports in numeric format. |
| `ss -tuna` | Show all TCP and UDP connections numerically. |
| `ss -anp` | Show all connections with process names. |

---

These commands **cover all major use cases** of `netstat` and `ss`. If you need **practical examples and outputs**, let me know! 


##  Netstat Command Usage & Examples

### 1 Display Active Connections
```bash
netstat
```
 **Example Output:**
```
Proto Recv-Q Send-Q Local Address Foreign Address State
tcp 0 0 192.168.1.10:22 192.168.1.2:54897 ESTABLISHED
```

### 2️ Show All Listening & Active Connections
```bash
netstat -a
```
 **Use Case:** Helps in identifying all services that are running.

### 3️ Display Numerical IP Addresses Instead of Hostnames
```bash
netstat -na
```
 **Use Case:** Faster output, useful in scripting.

### 4️ Show Only TCP Connections
```bash
netstat -t
```
 **Example:** Shows all active TCP connections.

### 5️ Show Only UDP Connections
```bash
netstat -u
```
 **Example:** Useful for troubleshooting DNS queries.

### 6️ Display Both TCP and UDP Connections
```bash
netstat -tu
```
 **Use Case:** View both types of network traffic.

### 7️ Show TCP & UDP Connections in Numeric Format
```bash
netstat -tun
```
 **Use Case:** Faster processing in scripts.

### 8️ Show Listening TCP & UDP Ports
```bash
netstat -ltun
```
 **Use Case:** Identifies which services are accepting connections.

### 9️ Display All Listening Services with Numeric IPs & Process Details
```bash
netstat -nltup
```
**Example Output:**
```
tcp 0 0 0.0.0.0:80 0.0.0.0:* LISTEN 1234/apache2
```

---

##  Alternative: `ss` Command Usage & Examples
Since `netstat` is deprecated in some distributions, `ss` is recommended:

### 1️ Show All Listening Ports
```bash
ss -l
```
 **Example:** View open ports on the system.

### 2️ Show All TCP Connections
```bash
ss -t
```
 **Example:** View current TCP sessions.

### 3️ Show All UDP Connections
```bash
ss -u
```
 **Example:** Check for UDP-based services.

### 4️ Show Detailed Connection Statistics
```bash
ss -s
```
 **Use Case:** Get an overview of system-wide connections.

### 5️ Show Listening TCP & UDP Ports
```bash
ss -ltun
```
 **Use Case:** Find which applications are listening for incoming connections.

### 6️ Show All Listening Services with Numeric IPs and Process Details
```bash
ss -nltup
```
 **Example Output:**
```
tcp LISTEN 0 128 0.0.0.0:22 0.0.0.0:* users:(("sshd",pid=1001,fd=3))
```

---

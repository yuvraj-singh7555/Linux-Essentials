# Network 🌐 Configuration

## Network Configuration Basics

The following commands help manage and verify network settings:

### Viewing Network Information

- `nmtui` - Opens a text-based user interface for configuring network connections.
- `hostname` - Displays or sets the system's hostname.
- `hostname -i` - Shows the system's IP address associated with the hostname.
- `hostname -I` - Lists all assigned IP addresses.
- `ip addr show` - Displays details of all network interfaces.
- `ifconfig` - Displays network interface configurations.
- `ip ad` - Similar to `ip addr show`, lists network interfaces and IPs.

### Checking Public IP Address

- `curl -4 ifconfig.me` - Retrieves the system's external IPv4 address.
- `curl -4 icanhazip.com` - Alternative way to check public IP.
- `cat /etc/resolv.conf` - Shows DNS resolver settings.
- `route -n` - Displays the kernel routing table.
- `ip route` - Displays and manipulates the system's routing table (part of the `iproute2` package).

## Configuring Static IP Address

To configure a static IP address using NetworkManager:

1. Navigate to the NetworkManager system connections directory:
   ```bash
   cd /etc/NetworkManager/system-connections/
   ```
2. Open the connection file with Vim:
   ```bash
   vim enp0s3.nmconnection
   ```
3. Modify the configuration file with a static IP:
   ```ini
   [connection]
   id=enp0s3
   uuid=668303d1-c039-30c9-82bf-0f3527891838
   type=ethernet
   autoconnect-priority=-999
   interface-name=enp0s3
   timestamp=1726179824

   [ethernet]

   [ipv4]
   address1=192.168.1.31/24,192.168.1.1
   dns=8.8.8.8;
   method=manual

   [ipv6]
   addr-gen-mode=eui64
   method=manual

   [proxy]
   ```
   - `address1=192.168.1.34/24` - Assigns `192.168.1.34` as the static IP with a subnet mask of `255.255.255.0` (`/24`) and sets the gateway to `192.168.1.1`.
   - `dns=8.8.8.8;8.8.4.4;` - Uses Google's public DNS.
   - `method=manual` - Configures IPv4 manually.

## Configuring Dynamic IP (DHCP)

1. Navigate to the NetworkManager system connections directory:
   ```bash
   cd /etc/NetworkManager/system-connections/
   ```
2. Open the connection file with Vim:
   ```bash
   vim enp0s3.nmconnection
   ```
3. Modify the configuration file:
   ```ini
   [connection]
   id=enp0s3
   uuid=a32babco-fbae-3689-b858-40d62bd6d445
   type=ethernet
   autoconnect-priority=-999
   interface-name=enp0s3
   timestamp=1739793171

   [ethernet]

   [ipv4]
   method=auto

   [ipv6]
   addr-gen-mode=eui64
   method=disabled

   [proxy]
   ```
   - `method=auto` enables DHCP, allowing the system to obtain an IP address automatically.

## Assigning Multiple IPs to a Single Network Interface

To assign multiple IP addresses to a single interface (`enp0s3`):

1. Navigate to the system connections directory:
   ```bash
   cd /etc/NetworkManager/system-connections/
   ```
2. Edit the connection file:
   ```bash
   vim enp0s3.nmconnection
   ```
3. Modify the configuration file:
   ```ini
   [connection]
   id=enp0s3
   uuid=a32babco-fbae-3689-b858-40d62bd6d445
   type=ethernet
   autoconnect-priority=-999
   interface-name=enp0s3
   timestamp=1739793171

   [ethernet]

   [ipv4]
   address1=192.168.1.34/24
   address2=192.168.1.35/24
   address3=192.168.1.36/24
   address4=192.168.1.37/24
   dns=8.8.8.8,8.8.4.4;
   gateway=192.168.1.1
   method=manual

   [ipv6]
   addr-gen-mode=eui64
   method=disabled

   [proxy]
   ```
   - Each additional IP (`.32, .33, .34`) is assigned to the same interface.
 

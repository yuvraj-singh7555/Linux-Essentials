# Linux Essentials

## Introduction to Linux
- UNIX, Linux, and Open Source
- What is Linux?
- History and Evolution of Linux
- Understanding the Linux Kernel
- Key Features of Linux
- Linux Distributions
- Directory Structure of Linux
- Linux Installation
- Login Methods in Linux
- Run Levels in Linux

## Linux Basic Commands
- Finding Your Way (`ls`, `pwd`, `cd`)
- Creating and Removing Directories and Files (`mkdir`, `touch`, `rmdir`, `rm`)
- Copying, Moving, and Renaming Files and Directories
- Using the `cat` Command
- Using the `less` and `more` Commands
- Pipes and Redirects
- Archiving and Compression
- Compression Tools (`zip`, `gzip`, `bzip`, `tar`, `7zip`)
- Archiving Tools
- Symbolic Links
- Shortcuts

## Text Editor
- `cat`
- `nano`
- `vi` / `vim`

## String Processing and Finding Files
### String Processing Commands:
- `head`
- `tail`
- `wc`
- `sort`
- `cut`
- `paste`
- `grep`
- `awk`
- `sed`

### Finding Files Commands:
- `tree`
- `find`
- `which`
- `whereis`

## Users, Groups, and Permissions
- Types of Shells
- Users and Groups
- `/etc/passwd` File
- `/etc/shadow` File
- `/etc/group` File
- `/etc/gshadow` File
- Adding Users
- Modifying User Accounts
- Deleting User Accounts
- Working with Groups
- Setting User Environments
- Root Login
- Sharing Superuser Privileges with others (`su` and `sudo` Commands)
- Switching User and Group
- File Permissions
- Directory Permissions
- Changing Permissions
- Setting Default Permissions
- SUID Bit
- SGID Bit
- Setting the Sticky Bit
- ACL Permissions

## Package Management
- Overview of RPM and SRPM Packages
- Explanation of Different Architectures
- Installing Packages Using RPM
- Understanding Repositories
  - Types of Repositories
- Installing Packages Using `yum`

## File System & Disk Management
- Types of Disks
- `parted` Utility
- `fdisk` Utility
- Mounting a File System
- The `/etc/fstab` File
- Quota Management
- SWAP (Partitions and Files)
- RAID Overview
  - Uses of RAID
  - RAID Levels
- Logical Volume Manager (LVM)

## Network Configuration and Controlling Services
- Network Configuration
- Network Tools
  - `traceroute`
  - `tracepath`
  - `netstat`
  - `ss`
- Network Clients
  - `ssh`
  - `scp`
  - `ftp`
  - `wget`
- `rsync`
- Checking the Status of Services
  - Is service active?
  - Is service enabled?
  - Listing the Active/Inactive State of Loaded Units
- Starting, Restarting, and Stopping Services

## Security, Process Management, and Monitoring Tools
### Securing Shell
- Change Default Port
- Prevent Root Access
- Public/Private Keys
- Managing IP Allow and Deny

### Job Management
- `jobs`, `ps`, `htop`

### Installing & Configuring Antivirus Software
- `ClamAV`
- `LMD` (Linux Malware Detect)

### Firewalls
- `iptables`
- `ufw` (Uncomplicated Firewall)

### Process Management
### Monitoring Tools
- `vmstat`
- `iostat`
- `lsof`
- `tcpdump`

---
### Contributing
Feel free to fork this repository and contribute to the guide by submitting pull requests.

### License
This project is licensed under the MIT License.

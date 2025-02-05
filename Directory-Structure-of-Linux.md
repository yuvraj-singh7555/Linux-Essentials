### **Linux Directory Structure**

| Directory | Purpose |
| --- | --- |
| `/` | Root directory, the top-most level of the file system. Contains all other directories. |
| `/bin` | Essential system binaries for basic commands (e.g., `ls`, `cp`, `mv`). |
| `/sbin` | System binaries for administrative tasks, usually executed by the root user (e.g., `fsck`, `reboot`). |
| `/etc` | Configuration files for the system and applications (e.g., network, user settings). |
| `/dev` | Device files representing hardware devices (e.g., `tty`, `sda`, `null`). |
| `/proc` | Virtual files providing process and kernel information, such as `/proc/cpuinfo` and `/proc/meminfo`. |
| `/home` | Home directories for regular users where personal files and configurations are stored. |
| `/root` | Home directory for the root user (administrator). |
| `/lib` | Shared libraries required by system binaries and programs to run. |
| `/lib64` | 64-bit shared libraries for modern systems, similar to `/lib` but for 64-bit architecture. |
| `/media` | Mount points for removable media (e.g., CD/DVD drives, USB drives). |
| `/mnt` | Temporary mount points for manually mounted devices (e.g., mounting a network share). |
| `/opt` | Optional application software and packages not part of the core system. |
| `/srv` | Service data provided by the system, such as web server data or FTP server data. |
| `/tmp` | Temporary files used by applications. Cleared on reboot. |
| `/usr` | User programs, data, and shared files. This directory contains most user utilities and applications. |
| `/var` | Variable data files that change during system operation (e.g., logs in `/var/log`, spools, cache). |

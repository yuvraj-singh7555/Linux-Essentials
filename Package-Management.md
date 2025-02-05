# Package Management in Linux

Package Managers are used to handle software installation, removal, and updates.

## Common Package Managers
- RPM
  - YUM, DNF
- DPKG
  - APT

### 1. Red Hat Package Manager (RPM)
- RPM is the default package manager for Red Hat-based distributions, such as RHEL (Red Hat Enterprise Linux), CentOS, Fedora, and others.
- It is an open packaging format that can be used on multiple Linux and UNIX systems, not just Red Hat-based ones.
- It is used for installing, uninstalling, upgrading, querying, listing, and checking RPM packages on Linux systems.
- It can handle software packages, documentation, and source code.

- **File Extension**: RPM packages end with the `.rpm` extension.


- **Two Types of RPM Files**:
    - **RPM (Binary RPM)**: Contains the compiled version of the application or libraries.
    - **SRPM (Source RPM)**: Contains the source code for the application. These are typically used for compiling the application from source on your system.
#### Common Commands
- Install a package:
  ```sh
  sudo rpm -i package.rpm
  ```
- Remove a package:
  ```sh
  sudo rpm -e package-name
  ```
- Query package:
  ```sh
  sudo rpm -q package-name
  ```
- Verify installed package:
  ```sh
  sudo rpm -V package-name
  ```
- List all installed packages:
  ```sh
  sudo rpm -qa
  ```

#### Architecture Types for Packages
- **i386**: 32-bit systems.
- **x86_64**: 64-bit systems.
- **noarch**: Platform-independent.

#### Contents of RPM Packages
- Application or libraries
- Documentation (man pages, manuals)
- Configuration files
- **SPEC File**: Metadata and instructions for creating the RPM package.

#### RPM Database
- Location: `/var/lib/rpm`
- This database contains information about the packages installed on the system, their version, and other metadata.

#### Package Name Format
- Example: `nginx-1.20.0-1.el7.ngx.x86_64.rpm`
  - **nginx**: Package name
  - **1.20.0**: Version
  - **1**: Release number
  - **el7**: Distribution version (Enterprise Linux 7)
  - **ngx**: Specific build for Nginx
  - **x86_64**: 64-bit architecture

### YUM/DNF
Front-end tools for RPM, resolving dependencies.

- Install a package:
  ```sh
  sudo yum install package-name
  ```
  or
  ```sh
  sudo dnf install package-name
  ```
- Update all packages:
  ```sh
  sudo yum update
  ```
  or
  ```sh
  sudo dnf update
  ```

---

### 2. Debian Package Manager (DPKG)
- **Used by**: Debian, Ubuntu
- **File Format**: `.deb`
- **Usage**: Handling Debian packages.

#### Common Commands
- Install a package:
  ```sh
  sudo dpkg -i package.deb
  ```
- Remove a package:
  ```sh
  sudo dpkg -r package-name
  ```
- List installed packages:
  ```sh
  sudo dpkg -l
  ```
- Query package:
  ```sh
  sudo dpkg -s package-name
  ```
- Fix broken dependencies:
  ```sh
  sudo apt-get install -f
  ```

#### Some Debian-based OS
Examples: Blackbox, Arch, Parrot, Kali, Debian, Ubuntu.

### APT (Advanced Package Tool)
Higher-level tool for managing Debian packages.

- Install a package:
  ```sh
  sudo apt install package-name
  ```
- Update package list:
  ```sh
  sudo apt update
  ```
- Upgrade installed packages:
  ```sh
  sudo apt upgrade
  ```

---

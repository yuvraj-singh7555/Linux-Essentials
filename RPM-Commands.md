# RPM (REDHAT PACKAGE MANAGE) Commands:

- **Check OS Details**:

  You can check your OS details using the following commands:

  ```bash
  # cat /etc/os-release
  # cat /etc/system-release
  # cat /etc/redhat-release
  # uname -a
  ```

  - The `uname -a` command prints all available system information.
    - `uname` prints the kernel name.
    - `-a` option prints all information about the system.

  **Example Output**:

  ```
  Linux localhost.localdomain 5.14.0-522.el9.x86_64 #1 SMP PREEMPT_DYNAMIC Sun Oct 20 13:04:34 UTC 2023 x86_64 x86_64 x86_64 GNU/Linux
  ```

  Breakdown:

  - **Linux**: Kernel name.
  - **localhost.localdomain**: Hostname of the system.
  - **5.14.0-522.el9.x86_64**: Kernel version.
    - **5.14.0**: Kernel version.
    - **522**: Patch level.
    - **el9**: Enterprise Linux 9 (RHEL 9).
    - **x86_64**: 64-bit architecture.
  - **#1 SMP PREEMPT_DYNAMIC**: Additional kernel build info.
    - **#1**: Build number.
    - **SMP**: Symmetric Multi-Processing support.
    - **PREEMPT_DYNAMIC**: Preemption model.
  - **Sun Oct 20 13:04:34 UTC 2023**: Build date and time.
  - **x86_64 x86_64 x86_64**: System architecture information.
  - **GNU/Linux**: Indicates a GNU/Linux operating system.

---

- **Identify Package Manager**:

  Run these commands to check which package manager your OS uses:

  ```bash
  # rpm --version
  # dnf --version
  # yum --version
  # dpkg --version
  # apt --version
  ```

  - If `rpm`, `yum`, or `dnf` return versions, your system uses RPM.
  - If `dpkg` or `apt` return versions, your system uses DPKG.

---

- **RPM Database Location**:

  ```bash
  # ls /var/lib/rpm
  ```

  - Files you might see:

    ```
    /var/lib/rpm/rpmdb.sqlite
    /var/lib/rpm/rpmdb.sqlite-shm
    /var/lib/rpm/rpmdb.sqlite-wal
    ```

  - These are SQLite database files used by RPM to store and manage installed packages.
  - You can view details of these files using SQLite browsers to see all packages and related information.

  **Files Explanation**:

  1. **rpmdb.sqlite** (Main RPM Database)
     - Contains all package metadata:
       - Installed packages
       - Package versions
       - Dependencies
       - File locations
       - Configuration files
     - Queried when running `rpm -qa`.

  2. **rpmdb.sqlite-shm** (Shared Memory File)
     - Temporary shared memory for SQLite transactions.
     - Improves read/write performance by caching queries.
     - Created dynamically and may disappear when not in use.

  3. **rpmdb.sqlite-wal** (Write-Ahead Log)
     - Temporarily stores uncommitted changes before writing to `rpmdb.sqlite`.
     - Ensures data consistency in case of a crash.
     - Cleared when changes are committed.

---

- **RPM Commands**

  - **Check RPM Version**:

    ```bash
    # rpm --version
    ```

    Output:

    ```
    RPM version 4.16.1.3
    ```

  - **View RPM Help**:

    ```bash
    # rpm --help
    ```

  - **Query Installed Packages**:

    - **Check if a Package is Installed**:

      ```bash
      # rpm -q package_name
      ```

      Example:

      ```bash
      # rpm -q python3
      ```

      - If installed:

        ```
        python3-3.9.7-2.el9.x86_64
        ```

      - If not installed:

        ```
        package python3 is not installed
        ```

    - **List All Installed Packages**:

      ```bash
      # rpm -qa
      ```

      - Count total packages:

        ```bash
        # rpm -qa | wc -l
        ```

      - List packages by install time (most recent first):

        ```bash
        # rpm -qa --last
        ```

      - View recently installed 10 packages:

        ```bash
        # rpm -qa --last | head
        ```

      - Search for a specific package:

        ```bash
        # rpm -qa | grep package_name
        ```

    - **Get Package Information**:

      ```bash
      # rpm -qi package_name
      ```

      - Provides detailed information about the package.

    - **List Files Installed by a Package**:

      ```bash
      # rpm -ql package_name
      ```

    - **List Configuration Files of a Package**:

      ```bash
      # rpm -qc package_name
      ```

    - **List Documentation Files of a Package**:

      ```bash
      # rpm -qd package_name
      ```

    - **List Dependencies Required by a Package**:

      ```bash
      # rpm -qR package_name
      ```

    - **List Capabilities Provided by a Package**:

      ```bash
      # rpm -q --provides package_name
      ```

    - **Dump Basic File Information of a Package**:

      ```bash
      # rpm -q --dump package_name
      ```

    - **Show States of Files Installed by a Package**:

      ```bash
      # rpm -qs package_name
      ```

    - **Query Package Owning a File**:

      ```bash
      # rpm -qf /path/to/file
      ```

      Example:

      ```bash
      # rpm -qf /usr/bin/nano
      ```

---

- **Download a Package**:

  ```bash
  # wget https://nginx.org/packages/rhel/9/x86_64/RPMS/nginx-1.26.2-2.el9.ngx.x86_64.rpm
  ```

  **Before Downloading**:

  - Verify the package's release, version, and architecture match your system.
  - Check package dependencies and ensure they are available.
  - Verify that the package does not conflict with existing installed packages.
  - Check the package signature to confirm authenticity.
  - Review changelogs or documentation for important updates or known issues.

---

- **Query Non-Installed Packages**

  - **Query Package File**:

    ```bash
    # rpm -qp package_file.rpm
    ```

    - Displays the name of the package inside the RPM file.

  - **Get Detailed Information About a Package File**:

    ```bash
    # rpm -qip package_file.rpm
    ```

    - Displays detailed information such as name, version, release, architecture, license, group, size, summary, vendor, packager, URL, description, etc.

  - **List Configuration Files in a Package File**:

    ```bash
    # rpm -qcp package_file.rpm
    ```

  - **List All Files in a Package File**:

    ```bash
    # rpm -qlp package_file.rpm
    ```

  - **List Documentation Files in a Package File**:

    ```bash
    # rpm -qdp package_file.rpm
    ```

  - **List Dependencies Required by a Package File**:

    ```bash
    # rpm -qRp package_file.rpm
    ```

  - **Show License Information of a Package File**:

    ```bash
    # rpm -qLp package_file.rpm
    ```

---

- **Verify Packages**

  - **Verify Integrity of Installed Packages**:

    ```bash
    # rpm -V package_name
    ```

    - Checks the integrity of installed RPM packages.
    - Verifies size, permissions, checksum, and timestamps.
    - No output means no changes detected.
    - Output format:

      ```
      SM5DLUGT c /path/to/file
      ```

      - Symbols indicate what has changed:

        - **S**: File Size differs
        - **M**: Mode differs (permissions)
        - **5**: MD5 checksum differs
        - **D**: Device major/minor number mismatch
        - **L**: ReadLink(2) path mismatch
        - **U**: User ownership differs
        - **G**: Group ownership differs
        - **T**: Modification time differs

      - **File Types**:

        - **c**: Configuration file

    - **Example**:

      ```
      S.5....T.  c /etc/ssh/sshd_config
      ```

      - Indicates size, MD5 checksum, and timestamp have changed for `/etc/ssh/sshd_config`, which is a configuration file.

  - **Verbose Verification**:

    ```bash
    # rpm -Vv package_name
    ```

    - Provides detailed verification, including unchanged files.

  - **Verify Package Ignoring Dependencies**:

    ```bash
    # rpm -V --nodeps package_name
    ```

---

### **Explanation of Runlevels**

In Linux systems, **runlevels** define the state or mode of the system, determining which services and processes are running. Each runlevel corresponds to a specific system configuration. Traditionally, Linux used **SysVinit** (System V initialization) for managing these runlevels. 

Here’s a brief overview of the common runlevels:



### **Command Overview: SysVinit Runlevels**

| **Runlevel** | **SysVinit Command (`init`)** | **Description**                                         |
|--------------|-------------------------------|---------------------------------------------------------|
| **0**        | `sudo init 0`                  | Halt the system (shutdown).                            |
| **1**        | `sudo init 1`                  | Single-user mode for system recovery or maintenance.    |
| **2**        | `sudo init 2`                  | Multi-user mode without a GUI (rarely used).            |
| **3**        | `sudo init 3`                  | Multi-user mode with networking (no GUI).               |
| **4**        | `sudo init 4`                  | Custom runlevel (rarely used).                         |
| **5**        | `sudo init 5`                  | Multi-user mode with GUI (graphical interface).         |
| **6**        | `sudo init 6`                  | Reboot the system.                                     |

### **Command Overview for `init`**

| **Action**                                | **SysVinit Command (`init`)**  |
|-------------------------------------------|-------------------------------|
| **Check the current runlevel**            | `runlevel`                    |
| **Switch to a specific runlevel**         | `sudo init <runlevel>`         |
| **Reboot the system**                     | `sudo init 6`                 |
| **Shutdown the system**                   | `sudo init 0`                 |
| **Single-user mode for recovery**         | `sudo init 1`                 |
| **Multi-user mode with networking**       | `sudo init 3`                 |
| **Graphical mode (GUI)**                  | `sudo init 5`                 |

### **Explanation:**
- **`sudo init <runlevel>`**: The command to change the system's runlevel. For example:
  - **`sudo init 3`**: Switches the system to multi-user mode with networking (runlevel 3).
  - **`sudo init 0`**: Shuts down the system (runlevel 0).
  - **`sudo init 6`**: Reboots the system (runlevel 6).
  
- **`runlevel`**: This command shows the current and previous runlevel of the system.

### **Important Notes:**
- The `init` command works only on **legacy systems** that use the **SysVinit** system. Modern Linux systems generally use **systemd**, which replaces runlevels with **targets** and uses the **`systemctl`** command.

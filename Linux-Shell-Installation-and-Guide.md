# Linux Shell Installation & Guide

## Overview
This repository provides a comprehensive guide to Linux shells, including their types, uses, and commands. It also includes instructions on how to install and change shells.

---

## What is a Shell?
A **shell** is a command-line interface that allows users to interact with the operating system. It interprets user commands and executes them.

---

## Types of Shells in Linux

### 1. **Bourne Shell (sh)**
- One of the earliest shells in Unix systems.
- Lightweight and efficient.
- Limited interactive features.

### 2. **Bourne Again Shell (bash)**
- Most commonly used shell in Linux.
- Supports scripting and job control.
- Has command history and auto-completion.

### 3. **C Shell (csh)**
- Syntax similar to C programming language.
- Better suited for scripting tasks.
- Includes job control and command history.

### 4. **Korn Shell (ksh)**
- Combines features of both Bourne and C shell.
- Improved scripting capabilities.
- Used in commercial Unix systems.

### 5. **Z Shell (zsh)**
- Extended version of `bash` with more features.
- Supports plugins and themes.
- Includes auto-correction and path expansion.

---

## Uses of Shell in Linux
- **Command Execution:** Runs system commands and scripts.
- **Scripting:** Automates repetitive tasks using shell scripts.
- **Process Management:** Starts, stops, and manages processes.
- **File Management:** Creates, moves, and deletes files.
- **System Administration:** Configures the system and manages users.

---

## How to Check Your Default Shell
```sh
echo $SHELL
```

---

## How to Change Your Shell
1. **List available shells:**
   ```sh
   cat /etc/shells
   ```

2. **Change the default shell:**
   ```sh
   chsh -s /bin/zsh   # Replace /bin/zsh with your desired shell
   ```

3. **Restart terminal or log out and back in for changes to take effect.**

---

## Essential Shell Commands

### 1. **File and Directory Commands**
- **`ls`** – List files and directories
  ```sh
  ls -l   # Long listing format
  ```
- **`cd`** – Change directory
  ```sh
  cd /home/user
  ```
- **`mkdir`** – Create a new directory
  ```sh
  mkdir myfolder
  ```
- **`rm`** – Remove files or directories
  ```sh
  rm myfile.txt
  ```

### 2. **Process Management Commands**
- **`ps`** – Display running processes
  ```sh
  ps aux
  ```
- **`kill`** – Terminate a process
  ```sh
  kill 1234   # Replace 1234 with the process ID
  ```

### 3. **User and Permission Commands**
- **`whoami`** – Display current user
  ```sh
  whoami
  ```
- **`chmod`** – Change file permissions
  ```sh
  chmod 755 myscript.sh
  ```
- **`chown`** – Change file ownership
  ```sh
  chown user:group myfile.txt
  ```

### 4. **Networking Commands**
- **`ping`** – Check connectivity to a server
  ```sh
  ping google.com
  ```
- **`curl`** – Fetch data from a URL
  ```sh
  curl -O http://example.com/file.zip
  ```

### 5. **Package Management Commands**
- **Ubuntu/Debian:**
  ```sh
  sudo apt update && sudo apt upgrade
  ```
- **CentOS/RHEL:**
  ```sh
  sudo yum update
  ```
- **Arch Linux:**
  ```sh
  sudo pacman -Syu
  ```

---

## Conclusion
This guide provides an introduction to Linux shells and essential commands. Mastering the shell enhances system administration and productivity.

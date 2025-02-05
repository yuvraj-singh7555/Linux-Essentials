Here is the enhanced version of your Linux commands with the respective copy code included for each:

---

### **BASIC LINUX COMMANDS**

1. **pwd**  
   Shows the current directory you are in.
   ```bash
   pwd
   ```

2. **ls**  
   Lists all files and directories in the current directory.
   ```bash
   ls
   ```

3. **info**  
   Provides detailed information about a command.
   ```bash
   info ls
   ```

4. **man**  
   Displays the manual or instructions on how to use a command.
   ```bash
   man ls
   ```

5. **ls --help**  
   Displays help information for the `ls` command, showing available options and their usage.
   ```bash
   ls --help
   ```

6. **ls -l**  
   Lists files and directories in long format, showing detailed information like file permissions, owner, size, and date modified.
   ```bash
   ls -l
   ```

7. **ls -a**  
   Lists all files, including hidden files (those starting with a dot `.`).
   ```bash
   ls -a
   ```

8. **ls -h**  
   Displays the file size in a human-readable format (e.g., MB, KB).
   ```bash
   ls -lh
   ```

9. **ls -R**  
   Lists files and directories recursively (i.e., shows the contents of subdirectories).
   ```bash
   ls -R
   ```

10. **ls -r**  
   Displays the directory contents in reverse order.
   ```bash
   ls -r
   ```

11. **cd**  
   Changes the current directory to the specified directory.
   ```bash
   cd downloads
   ```

12. **cd ..**  
   Moves one level up in the directory tree.
   ```bash
   cd ..
   ```

13. **mkdir foldername**  
   Creates a new directory with the specified name.
   ```bash
   mkdir new_folder
   ```

14. **clear**  
   Clears the terminal screen.
   ```bash
   clear
   ```

15. **/**  
   Refers to the root directory, the topmost directory in Linux.
   ```bash
   cd /
   ```

16. **touch filename**  
   Creates an empty file with the specified name.
   ```bash
   touch file.txt
   ```

17. **cat**  
   Displays the contents of a file in the terminal.
   ```bash
   cat file.txt
   ```

18. **cat > filename**  
   Allows you to create a file and add content to it. You can exit the editor by pressing `Ctrl + C`.
   ```bash
   cat > file.txt
   ```

19. **rmdir foldername**  
   Deletes an empty directory.
   ```bash
   rmdir foldername
   ```

20. **rm**  
   Deletes a file.
   ```bash
   rm file.txt
   ```

21. **rm -rf**  
   Forcefully deletes a directory and its contents, including subdirectories and files.
   ```bash
   rm -rf foldername
   ```

22. **mkdir -p**  
   Creates nested directories in a single command.
   ```bash
   mkdir -p folder1/folder2/folder3
   ```

23. **cp**  
   Copies files or directories.
   ```bash
   cp file.txt /home/user/
   ```

24. **cp -v**  
   Copies files with verbosity, showing each file as it's copied.
   ```bash
   cp -v file.txt /home/user/
   ```

25. **cp -f**  
   Forces copying, overwriting any existing files without asking for confirmation.
   ```bash
   cp -f file.txt /home/user/
   ```

26. **cp -r**  
   Copies directories recursively.
   ```bash
   cp -r folder1/ folder2/
   ```

27. **mv**  
   Moves or renames files and directories.
   ```bash
   mv oldname.txt newname.txt
   ```

28. **ln -s**  
   Creates a symbolic (soft) link to a file or directory.
   ```bash
   ln -s /path/to/file linkname
   ```

29. **ln**  
   Creates a hard link to a file or directory.
   ```bash
   ln /path/to/file hardlinkname
   ```

30. **less**  
   Displays file content page by page.
   ```bash
   less file.txt
   ```

31. **more**  
   Similar to `less`, but with limited scrolling capability.
   ```bash
   more file.txt
   ```

32. **date**  
   Displays the current date and time.
   ```bash
   date
   ```

33. **id**  
   Displays the current user's UID (User ID), GID (Group ID), and group memberships.
   ```bash
   id
   ```

34. **whoami**  
   Shows the username of the currently logged-in user.
   ```bash
   whoami
   ```

35. **who**  
   Displays who is logged into the system, along with information like login time and terminal.
   ```bash
   who
   ```

36. **who -a**  
   Displays detailed information about the logged-in users, including the last login time.
   ```bash
   who -a
   ```

37. **w**  
   Shows detailed information about the users logged into the system, including their current activity and last commands.
   ```bash
   w
   ```

38. **tty**  
   Displays the terminal device you are using.
   ```bash
   tty
   ```

39. **hostname**  
   Displays the current system's hostname.
   ```bash
   hostname
   ```

40. **hostname -a**  
   Displays all the hostnames associated with the system.
   ```bash
   hostname -a
   ```

41. **hostname -i**  
   Displays the IP address of the current machine.
   ```bash
   hostname -i
   ```

42. **hostname -I**  
   Displays all available IP addresses associated with the system.
   ```bash
   hostname -I
   ```

43. **ifconfig**  
   Displays network interface configurations, such as IP address, netmask, and MAC address.
   ```bash
   ifconfig
   ```

44. **uname**  
   Displays basic information about the system's kernel.
   ```bash
   uname
   ```

45. **uname -a**  
   Displays detailed system and kernel information.
   ```bash
   uname -a
   ```

46. **cat /etc/os-release**  
   Displays information about the current operating system.
   ```bash
   cat /etc/os-release
   ```

47. **lscpu**  
   Displays detailed information about the system's CPU architecture.
   ```bash
   lscpu
   ```

48. **lsusb**  
   Lists all USB devices connected to the system.
   ```bash
   lsusb
   ```

49. **lspci**  
   Displays information about the PCI devices connected to the system.
   ```bash
   lspci
   ```

50. **lsblk**  
   Lists all block devices, such as hard drives, partitions, and storage devices.
   ```bash
   lsblk
   ```

51. **cal**  
   Displays a calendar for the current month.  
   You can specify a year as an argument, like `cal 2020` to view the calendar for 2020.
   ```bash
   cal
   ```

52. **free -h**  
   Displays memory and swap usage in a human-readable format.
   ```bash
   free -h
   ```

53. **route -n**  
   Displays the system's routing table, including gateways and network interfaces.
   ```bash
   route -n
   ```

54. **cat /etc/resolv.conf**  
   Displays DNS nameserver information.
   ```bash
   cat /etc/resolv.conf
   ```

55. **history**  
   Shows a list of previously executed commands in the terminal.
   ```bash
   history
   ```

56. **uptime**  
   Displays the system's uptime, i.e., how long the system has been running.
   ```bash
   uptime
   ```

57. **exit / logout**  
   Logs out or exits the current session.
   ```bash
   exit
   ```

58. **shutdown**  
   Shuts down the system.  
   You can also use:
   - `shutdown -c` to cancel a shutdown.
   - `shutdown -P` for a proper shutdown.
   - `shutdown -h` for a halt shutdown (abrupt).
   - `shutdown -P now` for immediate shutdown.
   - `poweroff` to turn off the system.
   - `init 0` to shut the system down.
   - `init 6` to reboot the system.
   - `shutdown -r` to restart the system.

   ```bash
   shutdown
   ```

---

This format includes the command explanation along with its corresponding copy code for easy use.
kk5

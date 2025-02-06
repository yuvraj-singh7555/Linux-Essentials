
# File Permissions in Linux/Unix
File permissions define who can read, write, or execute a file. In Linux/Unix-like systems, file permissions are set for three different groups of users: the owner of the file, the group associated with the file, and others.
  ### Types of Permissions
   - **Read (r)**: Allows the file to be opened and read.
   - **Write (w)**: Allows modifying or deleting the file.
   - **Execute (x)**: Allows executing the file as a program.
  ### Categories of Users
   - **User (u)**: The owner of the file.
   - **Group (g)**: A set of users who share the same group.
   - **Others (o)**: All other users on the system.
  ### File Permission Format
  File permissions are often displayed as a string of characters such as:
    -**-rwxr-xr--**
  This string consists of 10 characters, with the following breakdown:
   - The first character represents the file type:
     - `-` for a regular file
     - `d` for a directory
     - `l` for a symbolic link
  
  - The remaining 9 characters represent the permissions for **user (owner)**, **group**, and **others** in the following order:
     - **User (Owner)**: The first three characters
     - **Group**: The next three characters
     - **Others**: The last three characters

  For example, `rwxr-xr--` means:
    - **User**: `rwx` (read, write, and execute permissions)
    - **Group**: `r-x` (read and execute permissions)
    - **Others**: `r--` (read permission)


  ### Numeric Representation of Permissions

  Permissions can also be represented by numeric values:
  | Permission | Numeric Value |
  |------------|---------------|
  | Read (r)   | 4             |
  | Write (w)  | 2             |
  | Execute (x)| 1             |

  Each permission type can be assigned a numeric value, and the sum of those values determines the permission setting.
  For example:
   - `rwx` = 4 + 2 + 1 = **7**
   - `r-x` = 4 + 0 + 1 = **5**
   - `r--` = 4 + 0 + 0 = **4**

  Thus, the permission `rwxr-xr--` corresponds to **755** in numeric form.

  ## Changing File Permissions
   You can use the `chmod` command to change file permissions. 

  ### Example Commands:
   - **Add execute permission for user**:

    - Set permissions to `rwxr-xr--` (755):
    
    - Set permission `rw-r--r--` (644):
    
    - Set permission `rwx------` (700) (Only the owner can read, write, and execute):
    
    - Set permission `rwxrwxrwx` (777) (Everyone has full access):
 
  - **Symbolic**: `chmod u+x file.txt` (adds execute permission to the user).

  - **Numeric**: `chmod 755 file.txt` (sets permissions to `rwxr-xr--`).


  ### Special Permissions
  1. **Setuid**: Allows a user to execute a file with the permissions of the file owner.
  2. **Setgid**: Allows a user to execute a file with the permissions of the group.
  3. **Sticky Bit**: Ensures that only the file owner can delete the file from a directory.

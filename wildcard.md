### Wildcards in Linux  

Wildcards are special characters used in Linux to represent unknown or variable values in filenames and commands. They allow users to efficiently search for, list, and manipulate multiple files at once without having to type each name explicitly. Wildcards are primarily used in conjunction with commands like `ls`, `cp`, `mv`, and `rm`, making file management more efficient.  

#### **Types of Wildcards in Linux**  

##### **1. Asterisk (`*`) – Matches Any Number of Characters**  
The asterisk (`*`) is the most commonly used wildcard in Linux. It represents zero or more characters in a filename or directory. This means that it can match multiple files at once, regardless of the characters in their names.  

- **Example:**  
  ```bash
  ls *.txt
  ```
  This command lists all files in the current directory that end with `.txt`.  

- **Another Example:**  
  ```bash
  rm file*
  ```
  This removes all files that start with "file", such as `file1.txt`, `file2.txt`, or `file_document.txt`.  

##### **2. Question Mark (`?`) – Matches Exactly One Character**  
The question mark (`?`) is used when a single character in a filename is unknown or variable. It matches exactly one character, making it useful for filtering files with slight differences in their names.  

- **Example:**  
  ```bash
  ls file?.txt
  ```
  This lists files like `file1.txt`, `fileA.txt`, and `fileB.txt` but not `file12.txt` because `?` only replaces a single character.  

##### **3. Square Brackets (`[]`) – Matches Any Single Character from a Set**  
Square brackets (`[]`) allow users to specify a set of possible characters to match in a filename. It replaces exactly one character but only with characters listed inside the brackets.  

- **Example:**  
  ```bash
  ls file[123].txt
  ```
  This matches `file1.txt`, `file2.txt`, and `file3.txt` but not `file4.txt`.  

- **Range Example:**  
  ```bash
  ls file[a-c].txt
  ```
  This matches `filea.txt`, `fileb.txt`, and `filec.txt` but not `filed.txt`.  

##### **4. Exclamation Mark (`!` or `^` Inside `[]`) – Negation in Character Sets**  
By adding an exclamation mark (`!`) or caret (`^`) inside square brackets, users can exclude certain characters instead of including them.  

- **Example:**  
  ```bash
  ls file[!123].txt
  ```
  This matches any `fileX.txt` where `X` is not `1`, `2`, or `3`.  

##### **5. Curly Braces (`{}`) – Expands Multiple Options**  
Curly braces (`{}`) are not traditional wildcards but are used for **brace expansion**, allowing users to specify multiple options at once.  

- **Example:**  
  ```bash
  echo {file1,file2,file3}.txt
  ```
  This expands to `file1.txt file2.txt file3.txt`.  

- **Range Example:**  
  ```bash
  echo {1..5}
  ```
  This expands to `1 2 3 4 5`.  

##### **6. Double Asterisk (`**`) – Recursive Matching (Bash 4.0+)**  
In newer versions of Bash (4.0+), enabling `globstar` allows the use of `**`, which searches recursively through directories.  

- **Example:**  
  ```bash
  shopt -s globstar  # Enable globstar if not already enabled
  ls **/*.txt
  ```
  This lists all `.txt` files in the current directory and all its subdirectories.  


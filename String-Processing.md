### **String Processing in Linux**

**Why is string processing used?**
String processing is commonly used to filter and extract specific parts of output from commands such as `ifconfig`, `ip a`, etc.

---

### **Displaying File Content**

1. **`head` Command**  
   The `head` command is used to display the first few lines of a file. By default, it shows the first 10 lines.
   ```bash
   head 1.txt   # Displays the first 10 lines of 1.txt
   head -n 5 1.txt   # Displays the first 5 lines of 1.txt
   head -n 3 1.txt   # Displays the first 3 lines of 1.txt
   head -c 50 1.txt   # Displays the first 50 bytes of 1.txt
   ```

   You can also display the first few lines from multiple files:
   ```bash
   head 1.txt messages /var/log/centos.rep   # Displays first 10 lines from all three files
   ```

2. **`tail` Command**  
   The `tail` command is used to display the last few lines of a file. It shows the last 10 lines by default.
   ```bash
   tail 1.txt messages passwd centos.rep   # Displays the last 10 lines of each file
   tail -f /var/log   # Displays the last 10 lines of log files and updates when new entries appear
   ```

---

### **Counting Lines, Words, and Characters: `wc` Command**

1. **`wc` Command**  
   The `wc` command counts the lines, words, and bytes in a file.
   ```bash
   wc 1.txt   # Output: lines words bytes
   wc -l 1.txt   # Counts the number of lines
   wc -w 1.txt   # Counts the number of words
   wc -c 1.txt   # Counts the number of bytes
   ```

2. **Counting for Multiple Files**
   ```bash
   wc *   # Counts lines, words, and bytes for all files
   ls -1   # Lists files in the directory
   wc -l   # Counts the number of files
   ```

---

### **Sorting Data: `sort` Command**

1. **Basic Sorting**
   ```bash
   sort test1.txt   # Sorts lines alphabetically
   ```

2. **Additional Sort Options**
   - **Sort in numeric order (for numbers)**
     ```bash
     sort -h test1.txt   # Sorts numbers in ascending order
     ```

   - **Sort in reverse order**
     ```bash
     sort -r test1.txt   # Sorts lines in reverse order
     ```

   - **Sort randomly**
     ```bash
     sort -R test1.txt   # Sorts lines randomly
     ```

   - **Remove duplicates**
     ```bash
     sort test1.txt | uniq -c   # Removes duplicates and shows their count
     ```

3. **Sorting by Specific Columns**
   ```bash
   sort -k 2 test1.txt   # Sorts by the second column
   ```

4. **Handling Delimited Files**
   ```bash
   sort -t ',' -k 2 test1.txt   # Sorts by the second column of a comma-separated file
   ```

5. **Sorting by Month**
   ```bash
   sort -M test1.txt   # Sorts by month names
   ```

---

### **Watching File Changes: `watch` Command**

- **Monitor the output of a command periodically**
  ```bash
  watch -n 5 date   # Displays the current date every 5 seconds
  watch -n 1 date   # Displays the current date every second
  ```

---

### **Filtering Text: `grep` Command**

1. **Basic Search**
   ```bash
   grep searchword filename   # Finds occurrences of 'searchword' in the file
   grep "root" /etc/passwd   # Finds 'root' in the /etc/passwd file
   ```

2. **Search in Multiple Files**
   ```bash
   grep root /etc/passwd /etc/shadow   # Finds 'root' in both files
   ```

3. **Ignore Case (Case-insensitive search)**
   ```bash
   grep -i root messages   # Finds both 'root' and 'Root'
   ```

4. **Search for Multiple Words**
   ```bash
   grep -E "(session|root|mounting)" var/log/messages   # Finds 'session', 'root', or 'mounting'
   ```

5. **Search for Words in the Same Line**
   ```bash
   grep "session" var/log/messages | grep root   # Finds lines containing both 'session' and 'root'
   ```

6. **Exclude a Word (Using `-v`)**
   ```bash
   grep "session" var/log/messages | grep -v root   # Finds lines with 'session' but not 'root'
   ```

7. **Search for a Word at the Beginning or End of a Line**
   - Word at the beginning of a line:
     ```bash
     grep "^root" var/log/messages   # Finds lines where 'root' appears at the start
     ```
   - Word at the end of a line:
     ```bash
     grep "root.$" var/log/messages   # Finds lines where 'root' appears at the end
     ```

8. **Search by Date**
   ```bash
   grep "^2sep" var/log/messages | grep root   # Finds logs for 'root' on 2nd September
   ```

---

### **Advanced `grep` Usage**

1. **Find Single Character After a Word**
   ```bash
   grep 'roo.' filename   # Finds 'roo' followed by any single character
   ```

2. **Find Multiple Characters After a Word**
   ```bash
   grep 'roo..' filename   # Finds 'roo' followed by two characters
   ```

3. **Find Empty Lines**
   ```bash
   grep '^$' filename   # Finds empty lines
   ```

4. **Exclude Lines Starting with `#` (e.g., Comments)**
   ```bash
   grep -v '^#' ssd_config   # Excludes lines starting with #
   ```

5. **Find Alphanumeric Characters**
   ```bash
   grep "[[:alnum:]]" filename   # Finds all alphanumeric characters
   ```

6. **Search for a Pattern from Another File**
   ```bash
   grep -f domain.txt url.txt   # Searches for domains from domain.txt in url.txt
   ```

---

### **Cutting Columns: `cut` Command**

1. **Extract Columns from CSV File**
   ```bash
   cut -d ',' -f 2 my-csv.csv   # Extracts the second column (e.g., names)
   cut -d ',' -f 1,3 my-csv.csv   # Extracts columns 1 and 3
   cut -d ',' -f 1-3 my-csv.csv   # Extracts columns 1 to 3
   ```

2. **Replace Commas with Spaces**
   ```bash
   cut my-csv.csv | tr ',' ' '   # Replaces commas with spaces
   ```

3. **Find Specific IP Address**
   ```bash
   ifconfig | grep 'inet' | cut -d ' ' -f 9   # Extracts the IPv4 address
   ```

---

### **Joining Files: `paste` Command**

1. **Combine Files Column-wise**
   ```bash
   paste name.txt surname.txt   # Joins columns from two files
   paste -d ' ' name.txt surname.txt   # Joins with space delimiter
   ```

2. **Save Output to a New File**
   ```bash
   paste -d ' ' name.txt surname.txt > fullname.txt   # Saves the output in fullname.txt
   ```

---

#  sed

              sed OPTIONS [SCRIPT] [INPUT_FILE]

              SCRIPT:

              [addr]X[options

                       X is a single-letter sed command

              [addr] can be a single line number, a regular expression, or a range of lines. If [addr] is specified, the command X will be expression only on the matched lines

              Additional [ options ] are used for some sed command

sed ‘20,25d’ input.txt > output.txt

              The following example deletes lines 20 to 25 in the input.

              20,25 is an address range

              d is the delete commans

SED commands

              a text                                          append text adter a line

              d                                                 delete the pattern

              i text                                          insert text before a line

              p                                                print the pattern space

              q [ exit-code ]                            (quit) Exit sed without processing any more commands to input

              s/regexp/replacement/[flags]                            (subsstitute) Match the regular-expansion against the content of the pattern space. If found, replace matched string with replacement.

Command Line operations

              -n                                          disable automatic printing; sed only produces output when explicitly told to via the p command.

              -e script                                 add script

              -r                                           use extended regular expression rather than basic regular expressions.

---

```bash
 # sed ‘1.2p’ /etc/passwd
```

              This will print line 1 and 2, two times and the rest of the file as same as it is

```bash
 # sed -n ‘1.2p’ /etc/passwd
```

              This command will only print line 1 and 2, the rest of the file will not be printed

```bash
 # sed -n ‘/^$/p’ /etc/passwd
```

              Print only empty lines

```bash
 # sed -n ‘/^$/!p’ /etc/passwd
```

             Do not print empty lines

```bash
 # sed -n '1,$p' /etc/passwd
```

             Print all lines 

```bash
 # sed -n '$p' /etc/passwd
```

             This will only print last line

```bash
 # sed -n '5,8!p' /etc/passwd
```

              Do not print lines 5 to 8

```bash
 # sed '5,$d' /etc/passwd
```

              Do not print lines 5 to last / print lines 1 to 4

---

### Pattern Matching / Pattern Searching

```bash
 # sed -n '/root/p' /etc/passwd
```

            Matching `root` in given file

```bash
 # sed -n '/root/,+3p' /etc/passwd
```

            Print lines where `root` is matched and print next 3 lines where `root` is matched 

---

### Find and replace

```bash
 # sed -n 's/sbin/SBIN' /etc/passwd
```

              Searching `sbin` and replacing it with `SBIN`  ( This will only replace first match in a single lines )

```bash
 # sed -n 's/root/ROOT/gp' /etc/passwd
```

            `g` Means global, every single match of the file will be replaced with the word we are replacing 

```bash
 # sed -n 's/root/ROOT/1p' /etc/passwd
```

             Match `root` in line in given file and replace only first `root` with`ROOT` 

```bash
 # sed -n 's/root/ROOT/2p' /etc/passwd
```

             Match `root` in line in given file and replace only second `root` with`ROOT` 

```bash
 # echo “Welcome To Presidential Suite” | sed ‘s/\(\b[A-Z]\)/\(\1\)/g’
```

            Output will be :
           `(W)elcome (T)o (P)residential (S)uite`

```bash
 # sed ‘4 s/sbin/SBIN/’ file_name.txt
```

            This will replace `sbin` to `SBIN` in line number `4`

```bash
 # sed G file_name.txt
```

            Adds an empty line after every line in the file.

```bash
 # sed 'G;G;G' file_name.txt
```

           This will add 3 empty lines after every line in the file.

---

### Append

```bash
 # sed ‘/arnold/a ARNOLD User’ file_name.txt
```

           This will add `ARNOLD User` after `arnold` in the given file

```bash
 # sed ‘2a ARNOLD User’ file_name.txt
```

           This will add `ARNOLD User` after the second line of the given file

```bash
 # sed ‘5a ARNOLD User’ file_name.txt
```

           This will add `ARNOLD User` after the fifth line of the given file

```bash
 # sed ‘5!a ARNOLD User’ file_name.txt
```

           This will add `ARNOLD User` after every line except fifth line of the given file

```bash
 # sed ‘1,5a ARNOLD User’ file_name.txt
```

           This will add `ARNOLD User` after every line between 1 to 5th line of the given file 

---

### prepend

```bash
 # sed ‘1i ARNOLD User’ file_name.txt
```

           This will add `ARNOLD User` before the first line of the given file

```bash
 # sed ‘5!i ARNOLD User’ file_name.txt
```

           This will add `ARNOLD User` before every line except fifth line of the given file

```bash
 # sed ‘1i——————————————————————’ filename.txt
```

            This will make a line after line 1

```bash
 # sed ‘1,$i——————————————————————’ filename.txt
```

            This will make a line after every line

---

```bash
 # sed ‘/arnold/d’ file_name.txt
```

             `d` is for `delete` This will not print `arnold` in the file output

```bash
 # sed ‘/\tarnold/d’ file_name .txt
```

            Do not print `arnold` before which `tab` key is used

### Using character classes

```bash
 # sed ‘/[[:space:]]arnold/d’ filename.txt
```

            This will `NOT` print lines where `arnold` appears after a `ENTER` (at the start of a new line) `SPACE` and `TAB` key.

```bash
 # sed ‘[0-9]/d’ filename.txt
```

              Do `NOT` print output line which has given range of numbers in it.

```bash
 # sed ‘/[[:digit:]]/p’ filename.txt
```

             This will only print output which has digits

```bash
 # sed ‘/[[:digit:]]/d’ filename.txt
```

             This will NOT print output which has digits

```bash
 # sed ‘/[a-zA-Z]/d’ filename.txt
```

            Delete all lines containing alphabets A to Z capital to small 

```bash
 # sed ‘/[A-Z]/d’ filename.txt
```

            Delete all lines containing alphabets A to Z capital or Uppercase

```bash
 # sed ‘/\//d’ filename.txt
```

            Delete all lines containing `Slash (/)`  

```bash
 # sed ‘/\thr/d’ filename.txt
```

            Delete all lines containing`hr` after `TAB` key

---

### Change or replace

```bash
 # sed ‘/arnold/c ARNOLD User’ filename.txt
```

             This will change or replace `arnold` to `ARNOLD User`

```bash
 # sed '1c ARNOLD' filename.txt
```

             This will change or replace `arnold` to `ARNOLD` Only in line 1  

```bash
 # sed '1,5c ARNOLD' filename.txt
```

             This will change or replace `arnold` to `ARNOLD` Only in line range 1 to 5 

---

### Quit or exit file

```bash
 # sed ‘/arnold/q’ filename.txt
```

             This will `Quit` the file when `arnold` is found / printed

---

### Exit status code

           The status code of a successfully ran command is `0` , To make any status code of a successful command rather than `0` Use command below

```bash
 # sed ‘/arnold/q2’ filename.txt
 # echo $?
```

            The output of status code of command will be `2`

---

### Perform the shell command

```bash
 # sed ‘1e date’ /etc/passwd
```

           This will generate output of `date` command at first line of `/etc/passwd` file output

```bash
 # sed ‘$e date’ /etc/passwd
```

           This will generate output of `date` command at last line of `/etc/passwd` file output

```bash
 # sed ‘1e echo -n "Date: "; date’ filename.txt
```

           This will `echo` `date` then output of `date` command at first line of `filename.txt` file output

```bash
 # sed ‘1,3e id’ filename.txt
```

           This will generate output of `id` command at first to third line of `filename.txt` file output

### Substitute

```bash
# echo “one five three” | sed ‘s/five/two/’
```

            This will search five then replace it with two

```bash
 # sed ‘s/arnold/ARNOLD/’ filename.txt
```

            This will search  `arnold` and replace it with `ARNOLD` in the given file

```bash
# echo “Arnold user UID 1000” | sed ‘s/[[:digit:]]\+/***/’
```

          This will replace the digits with three stars ( *** ) ; Output will be :
          `Arnold user UID ***`

```bash
# echo “Arnold user UID 1000” | sed ‘s/[[:digit:]]/*****/’
```

          This will replace only first digit with five stars ( ***** ) ; Output will be :
          `Arnold user UID *****000`

```bash
# echo “Arnold user UID 1000” | sed ‘s/[0-9]\+/*****/’
```

           Using Pattern instead of Character class;Output will be :
          `Arnold user UID *****`

```bash
# sed ‘s/[0-9]\+/*****/g’ filename.txt
```

           This will replace all the digits of the file with four stars

```bash
 # sed ‘s/[[:digit:]]\+/***/g’ filename.txt
```

This will replace all of the digits of the given file with three stars 

```bash
 # sed ‘s/arnold/Arnold/ & & & &/’ filename.txt
```

           This will repeat `Arnold arnold arnold arnold arnold` when `arnold` is found in the given file ( Depends on the number of & symbol we provided )

---

### Multiple sed commands [ -e ]

```bash
 # sed -ne ‘/arnold/p’ -ne ‘/root/p’ filename.txt
```

```bash
 # sed -e ‘/arnold/a "+++++++++++++++++++++" ’ -e ‘/arnold/i "---------------------" ’ filename.txt
```

             This command will append `+++++++++++++++++++++` and prepend `---------------------` at the same time when the `arnold` word is found in the given file.

### Saving the changes [ -i ]

```bash
 # sed -i -e ‘/arnold/a "+++++++++++++++++++++" ’ -e ‘/arnold/i "---------------------" ’ filename.txt
```

            Using -i will save the changes in the file

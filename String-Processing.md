Sure, here's a more organized and simplified version of your note, with the relevant commands formatted properly:

---

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


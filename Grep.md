### **Grep Command in Linux**  
The `grep` command is used for searching patterns in files. It supports wildcards, regular expressions, and various options for filtering results.  

---

## **1️⃣ Basic `grep` Syntax**
```bash
grep [OPTIONS] PATTERN [FILE...]
```

✅ **Example:** Search for `"error"` in a file  
```bash
grep "error" logfile.txt
```
---

## **2️⃣ Grep with Patterns**  
### **Match Exact Word (`-w`)**  
```bash
grep -w "error" logfile.txt
```
✔ Matches `error`, but not `errors` or `erroneous`.

### **Case-Insensitive Search (`-i`)**  
```bash
grep -i "error" logfile.txt
```
✔ Matches `error`, `ERROR`, `Error`, etc.

### **Count Matches (`-c`)**  
```bash
grep -c "error" logfile.txt
```
✔ Shows how many lines contain `"error"`.

### **Show Line Numbers (`-n`)**  
```bash
grep -n "error" logfile.txt
```
✔ Displays line numbers of matching lines.

---

## **3️⃣ Grep with Wildcards**  
Wildcards are useful when searching across multiple files.  

### **Search in All `.txt` Files**  
```bash
grep "error" *.txt
```
✔ Searches for `"error"` in all `.txt` files.

### **Search in Files with Specific Prefix**  
```bash
grep "error" log*.txt
```
✔ Searches in files like `log1.txt`, `log2.txt`, etc.

### **Recursive Search (`-r`) in Directories**  
```bash
grep -r "error" /var/logs/
```
✔ Searches `"error"` inside all files in `/var/logs/` folder.

### **Exclude Certain Files (`--exclude`)**  
```bash
grep -r --exclude="*.log" "error" .
```
✔ Searches `"error"` in all files except `.log` files.

---

## **4️⃣ Grep with Regular Expressions (`-E`)**  
### **Search Multiple Words (`|`)**  
```bash
grep -E "error|fail" logfile.txt
```
✔ Matches lines containing `"error"` or `"fail"`.

### **Match Start of Line (`^`)**  
```bash
grep "^error" logfile.txt
```
✔ Finds lines that **start** with `"error"`.

### **Match End of Line (`$`)**  
```bash
grep "error$" logfile.txt
```
✔ Finds lines that **end** with `"error"`.

---

## **5️⃣ Useful Options**  
| Option | Description |
|--------|-------------|
| `-w` | Match whole words only |
| `-i` | Ignore case |
| `-n` | Show line numbers |
| `-r` | Recursive search |
| `-c` | Count matching lines |
| `-l` | Show filenames with matches |
| `--color=auto` | Highlight matching words |

---

### **🎯 Summary**
🔹 `grep` searches for patterns in files.  
🔹 Wildcards (`*`, `?`) help search in multiple files.  
🔹 `-w`, `-i`, `-n`, and `-r` enhance search capabilities.  
🔹 Regular expressions (`-E`) allow advanced pattern matching.  

🚀 **Master `grep` for fast and efficient text searching in Linux!** 💡

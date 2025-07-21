## 🗂️ Keywords  
View a file's contents  
Look at the start of a file  
List everything below a directory  
Help for a command  
Skip first 6 lines and print from 7th to end  
Columns from a file  
Lines containing specific values  
Merge Lines

---

## 🐧 Bash Shell Scripting – Quick Reference (Part 3)

### ✅ View a file's contents
- `cat agarwal.txt`

---

### ✅ Look at the start of a file
```bash
head seasonal/summer.csv
head -n 3 seasonal/summer.csv
```

---

### ✅ List everything below a directory
- `ls -R`

> In order to see everything underneath a directory, no matter how deeply nested it is,  
> you can give `ls` the flag `-R` (which means "recursive").

---

### ✅ Help for a command
- `man head`

---

### ✅ Skip first 6 lines and print from 7th to end
- `tail -n +7 file_name`

---

### ✅ Columns from a file
```bash
cut -f 2-5,8 -d , values.csv
```

> This means "select columns 2 through 5 and column 8, using a comma as the separator".  
> `cut` uses `-f` (fields) to specify columns and `-d` (delimiter) to specify the separator.

---

### ✅ Lines containing specific values
```bash
grep bicuspid seasonal/winter.csv
```

Common flags for `grep`:
- `-c` → print a count of matching lines  
- `-h` → don’t print filenames when searching multiple files  
- `-i` → ignore case (e.g., "Regression" and "regression" both match)  
- `-l` → print only names of files that contain matches  
- `-n` → print line numbers for matching lines  
- `-v` → invert match: show lines that **don’t** match

---

### ✅ Merge Lines
```bash
paste file1 file2
```

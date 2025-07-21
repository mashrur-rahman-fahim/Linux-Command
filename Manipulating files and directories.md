## 🗂️ Keywords  
PWD  
ls  
Relative vs Absolute path  
Move up a directory  
Copy/move files (multiple)  
Rename file  
Delete file (multiple)  
Create and delete directories

---

## 🐧 Bash Shell Scripting – Quick Reference (Part 4)

### ✅ PWD
- To find out where you are in the filesystem, run the command:
```bash
pwd
```

---

### ✅ ls
- Use `ls` with appropriate arguments to list files in the directory:
```bash
ls
```

---

### ✅ Relative vs Absolute path
- If you are in the directory `/home/repl`, the **relative** path `seasonal`  
  refers to the same location as the **absolute** path `/home/repl/seasonal`.

---

### ✅ Move up a directory
- If you are in `/home/repl/seasonal`, where does this take you?

```bash
cd ~/../.
```

- It navigates to `/home`.

---

### ✅ Copy/move files (multiple)
```bash
cp seasonal/autumn.csv seasonal/winter.csv backup
mv seasonal/autumn.csv seasonal/winter.csv backup
```

---

### ✅ Rename file
```bash
mv course.txt old-course.txt
```

---

### ✅ Delete file (multiple)
```bash
rm thesis.txt backup/thesis-2017-08.txt
```

---

### ✅ Create and delete directories
```bash
mkdir directory_name
rmdir directory_name
```

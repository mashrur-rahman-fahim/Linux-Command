## 🗂️ Keywords  
Edit a file  
Run bash script  
Shell parameters ($@, $1, $2...)  
Write loops in shell

---

## 🐧 Bash Shell Scripting – Quick Reference (Part 5)

### ✅ Edit a file
- Open a file in the terminal text editor:
```bash
nano filename
```

#### Nano shortcuts:
- `Ctrl + K`: delete a line  
- `Ctrl + U`: un-delete a line  
- `Ctrl + O`: save the file (_O for output_)  
  → Press `Enter` to confirm the filename  
- `Ctrl + X`: exit the editor

---

### ✅ Run bash script
```bash
bash dates.sh
bash count-records.sh seasonal/*.csv > num-records.out
```

- `$@` allows a script to accept multiple command-line arguments.
- You can also use `$1`, `$2`, etc., to refer to individual arguments.

Example script: `column.sh`
```bash
cut -d , -f $2 $1
```

Usage:
```bash
bash column.sh seasonal/autumn.csv 1
```

---

### ✅ Write loops in shell

This loop will:
- Show the 2nd line of each file
- Then the last line of each file

```bash
for filename in $@
do
    head -n 2 $filename | tail -n 1
    tail -n 1 $filename
done
```

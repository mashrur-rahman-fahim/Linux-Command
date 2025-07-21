## 🗂️ Keywords  
Store a command's output in a file  
Use a command's output as an input  
Count the records in a file  
Specify many files at once  
Wildcards  
Sort lines of text (Uniq)

---

## 🐧 Bash Shell Scripting – Quick Reference (Part 2)

### ✅ Store a command's output in a file
- `head -n 5 seasonal/summer.csv > top.csv`

---

### ✅ Use a command's output as an input
- `head -n 5 seasonal/summer.csv | tail -n 3`

> Suppose you want to get lines from the middle of a file.  
> More specifically, suppose you want to get lines 3–5 from one of our data files.  
> You can start by using `head` to get the first 5 lines and then use `tail` to select the last 3.

---

### ✅ Count the records in a file
- The command `wc` (short for "word count") prints the number of **c**haracters, **w**ords, and **l**ines in a file.
- You can make it print only one of these using the flags:  
  - `-c` for characters  
  - `-w` for words  
  - `-l` for lines

---

### ✅ Specify many files at once
```bash
cut -d , -f 1 seasonal/*
cut -d , -f 1 seasonal/*.csv
```

---

### ✅ Wildcards
- `?` matches a single character  
  → `201?.txt` matches `2017.txt`, `2018.txt`, but not `2017-01.txt`

- `[...]` matches any one of the characters inside  
  → `201[78].txt` matches `2017.txt` or `2018.txt`, but not `2016.txt`

- `{...}` matches any of the comma-separated patterns  
  → `{*.txt, *.csv}` matches files ending in `.txt` or `.csv`, not `.pdf`

---

### ✅ Sort lines of text (Uniq)
- `sort` puts data in ascending alphabetical order by default.

Flags for `sort`:
- `-n` → sort numerically  
- `-r` → reverse the order  
- `-b` → ignore leading blanks  
- `-f` → fold case (case-insensitive)

- `uniq` removes **adjacent** duplicated lines.  
- `uniq -c` displays each unique line with the number of times it occurs.

Example:
```bash
cat file.txt | sort | uniq -c
```

## 🗂️ Keywords
Use set and grep with a pipe to display the value of HISTFILESIZE  
Print a variable's value  
The shell stores information  
Repeat a command many times  
Repeat a command on CSV files

---

## 🐧 Bash Shell Scripting – Quick Reference

### ✅ Use `set` and `grep` with a pipe to display the value of `HISTFILESIZE`
- set | grep HISTFILESIZE

---

### ✅ Print a variable's value
- echo $DataCamp

---

### ✅ The shell stores information

- The other kind of variable is called a **shell variable**, which is like a local variable in a programming language.
- To create a shell variable, you simply assign a value to a name:

```bash
training=seasonal/summer.csv
```

- _Without_ any spaces before or after the `=` sign.  
  Once you have done this, you can check the variable's value with:

```bash
echo $training
```

```text
seasonal/summer.csv
```

---

### 🔁 Repeat a command many times
```bash
for filetype in gif jpg png; do echo $filetype; done
```

---

### 🔁 Repeat a command on CSV files
```bash
for filename in seasonal/*.csv; do echo $filename; done
```

```bash
for file in seasonal/*.csv; do head -n 2 $file | tail -n 1; done
```

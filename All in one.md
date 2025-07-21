## 🗂️ Keywords  
PWD  
ls  
Relative vs Absolute path  
Move up a directory  
Copy/move files (multiple)  
Rename file  
Delete file (multiple)  
Create and delete directories  
View a file's contents  
Look at the start of a file  
List everything below a directory  
Help for a command  
Skip first 6 lines and print from 7th to end  
Columns from a file  
Lines containing specific values  
Merge Lines  
Store a command's output in a file  
Use a command's output as an input  
Count the records in a file  
Specify many files at once  
Wildcards  
Sort lines of text (Uniq)  
Use set and grep with a pipe to display the value of HISTFILESIZE  
Print a variable's value  
The shell stores information  
Repeat a command many times  
Repeat a command on CSV files  
Edit a file  
Run bash script  
Shell parameters ($@, $1, $2...)  
Write loops in shell

---

## 🐧 Bash Shell Scripting – Quick Reference

### ✅ PWD
- To find out where you are in the filesystem, run the command:
pwd

---

### ✅ ls
- Use `ls` with appropriate arguments to list files in the directory:
ls

---

### ✅ Relative vs Absolute path
- If you are in the directory `/home/repl`, the **relative** path `seasonal`  
  refers to the same location as the **absolute** path `/home/repl/seasonal`.

---

### ✅ Move up a directory
- If you are in `/home/repl/seasonal`, where does this take you?
cd ~/../.
- It navigates to `/home`.

---

### ✅ Copy/move files (multiple)
cp seasonal/autumn.csv seasonal/winter.csv backup  
mv seasonal/autumn.csv seasonal/winter.csv backup

---

### ✅ Rename file
mv course.txt old-course.txt

---

### ✅ Delete file (multiple)
rm thesis.txt backup/thesis-2017-08.txt

---

### ✅ Create and delete directories
mkdir directory_name  
rmdir directory_name

---

### ✅ View a file's contents
cat agarwal.txt

---

### ✅ Look at the start of a file
head seasonal/summer.csv  
head -n 3 seasonal/summer.csv

---

### ✅ List everything below a directory
- `ls -R`

> In order to see everything underneath a directory, no matter how deeply nested it is,  
> you can give `ls` the flag `-R` (which means "recursive").

---

### ✅ Help for a command
man head

---

### ✅ Skip first 6 lines and print from 7th to end
tail -n +7 file_name

---

### ✅ Columns from a file
cut -f 2-5,8 -d , values.csv

> This means "select columns 2 through 5 and column 8, using a comma as the separator".  
> `cut` uses `-f` (fields) to specify columns and `-d` (delimiter) to specify the separator.

---

### ✅ Lines containing specific values
grep bicuspid seasonal/winter.csv

Common flags for `grep`:  
- `-c` → print a count of matching lines  
- `-h` → don’t print filenames when searching multiple files  
- `-i` → ignore case (e.g., "Regression" and "regression" both match)  
- `-l` → print only names of files that contain matches  
- `-n` → print line numbers for matching lines  
- `-v` → invert match: show lines that **don’t** match

---

### ✅ Merge Lines
paste file1 file2

---

### ✅ Store a command's output in a file
head -n 5 seasonal/summer.csv > top.csv

---

### ✅ Use a command's output as an input
head -n 5 seasonal/summer.csv | tail -n 3

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
cut -d , -f 1 seasonal/*  
cut -d , -f 1 seasonal/*.csv

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
cat file.txt | sort | uniq -c

---

### ✅ Use `set` and `grep` with a pipe to display the value of `HISTFILESIZE`
set | grep HISTFILESIZE

---

### ✅ Print a variable's value
echo $DataCamp

---

### ✅ The shell stores information
- The other kind of variable is called a **shell variable**, which is like a local variable in a programming language.  
- To create a shell variable, you simply assign a value to a name:

training=seasonal/summer.csv

- _Without_ any spaces before or after the `=` sign.  
  Once you have done this, you can check the variable's value with:

echo $training

Example output:  
seasonal/summer.csv

---

### 🔁 Repeat a command many times
for filetype in gif jpg png; do echo $filetype; done

---

### 🔁 Repeat a command on CSV files
for filename in seasonal/*.csv; do echo $filename; done

for file in seasonal/*.csv; do head -n 2 $file | tail -n 1; done

---

### ✅ Edit a file
- Open a file in the terminal text editor:
nano filename

#### Nano shortcuts:
- `Ctrl + K`: delete a line  
- `Ctrl + U`: un-delete a line  
- `Ctrl + O`: save the file (_O for output_)  
  → Press `Enter` to confirm the filename  
- `Ctrl + X`: exit the editor

---

### ✅ Run bash script
bash dates.sh  
bash count-records.sh seasonal/*.csv > num-records.out

- `$@` allows a script to accept multiple command-line arguments.  
- You can also use `$1`, `$2`, etc., to refer to individual arguments.

Example script: `column.sh`  
cut -d , -f $2 $1

Usage:  
bash column.sh seasonal/autumn.csv 1

---

### ✅ Write loops in shell

This loop will:  
- Show the 2nd line of each file  
- Then the last line of each file

for filename in $@  
do  
    head -n 2 $filename | tail -n 1  
    tail -n 1 $filename  
done

# practice-shell-scripting
practice-shell-scripting


# 🐧 Shell Scripting Practice

## 📌 About This Repository

Welcome to my **Shell Scripting Practice** repository!

This repository contains Bash Shell Scripting concepts, practical examples, Linux commands, and automation scripts.

The main objective of this repository is to improve my Linux and Bash scripting skills through hands-on practice, troubleshooting, and real-world automation scenarios.

The repository covers **Beginner to Advanced Shell Scripting**, including practical use cases in **Production Support, System Administration, and DevOps**.

---

## 🛠️ Technologies and Tools

- **Operating System:** Ubuntu Linux (WSL2)
- **Scripting Language:** Bash
- **Editor:** Vim / Vi, Visual Studio Code
- **Version Control:** Git
- **Repository Hosting:** GitHub
- **Tools:** grep, awk, sed, find, cut, sort, uniq

---

## 📚 Shell Scripting Topics

### 1. Linux Fundamentals
- Linux file system
- Basic Linux commands
- File and directory management
- File permissions
- chmod and chown
- Absolute and relative paths
- Input and output redirection

### 2. Shell Scripting Basics
- What is Shell Scripting?
- Bash interpreter and Shebang (`#!/bin/bash`)
- Creating and executing shell scripts
- Shell variables
- Environment variables
- Command-line arguments
- Exit status and exit codes
- Comments in shell scripts

### 3. Operators
- Arithmetic operators
- Relational operators
- Logical operators
- String operators
- Redirection operators (`>`, `>>`)
- Pipe operator (`|`)
- Logical AND (`&&`)
- Logical OR (`||`)

### 4. Conditional Statements
- if statement
- if-else statement
- if-elif-else statement
- Nested if statements
- case statements
- File and directory validation

### 5. Loops
- for loop
- while loop
- until loop
- Nested loops
- break statement
- continue statement

### 6. Functions
- Creating functions
- Calling functions
- Function parameters
- Return status
- Local and global variables

### 7. File Handling
- Creating files
- Reading files
- Writing into files
- Appending content
- Deleting specific lines
- Searching files
- Checking file existence
- File permissions

### 8. Text Processing
- grep command
- awk command
- sed command
- cut command
- sort command
- uniq command
- wc command
- head and tail commands

### 9. Advanced Shell Scripting
- Arrays
- String manipulation
- Regular expressions
- Command substitution
- Process substitution
- Error handling
- Debugging using `bash -x`
- Exit codes
- Logging

### 10. Automation and DevOps
- Application log monitoring
- Disk space monitoring
- CPU and memory monitoring
- Service status checking
- Application health checks
- Process monitoring
- File backup automation
- Cron job scheduling
- Docker automation
- Git automation
- Deployment automation

---

## 📂 Repository Structure

The following is the planned repository structure as more scripts are added.

```text
practice-shell-scripting/
│
├── README.md
│
├── basics/
│   ├── hello.sh
│   ├── variables.sh
│   └── arguments.sh
│
├── conditions/
│   ├── if_else.sh
│   └── file_check.sh
│
├── loops/
│   ├── for.sh
│   ├── while.sh
│   └── until.sh
│
├── file-handling/
│   ├── write.sh
│   ├── verify.sh
│   └── delete.sh
│
├── text-processing/
│   ├── grep.sh
│   ├── awk.sh
│   └── sed.sh
│
├── functions/
│   └── functions.sh
│
└── devops/
    ├── disk_monitor.sh
    ├── log_monitor.sh
    ├── service_check.sh
    └── backup.sh
```

---

## 💻 Practical Shell Scripting Examples

### Example 1: Write Content into Multiple Files

**Script: `write.sh`**

```bash
#!/bin/bash

cd /home/amya/shellscript_practice || exit 1

for folder in a b c d e
do
    echo "This is my new extra line inside $folder" >> "$folder"
done
```

**Explanation:**

- `for` iterates through files a, b, c, d, and e.
- `echo` generates the text.
- `>>` appends content without overwriting existing data.
- `done` terminates the loop.

---

### Example 2: Read Multiple Files

**Script: `verify.sh`**

```bash
#!/bin/bash

cd /home/amya/shellscript_practice || exit 1

for folder in a b c d e
do
    echo "Contents of file $folder:"
    cat "$folder"
done
```

**Explanation:**

- `cat` displays the contents of each file.
- The `for` loop processes all five files.

---

### Example 3: Delete a Specific Line

**Script: `delete.sh`**

```bash
#!/bin/bash

cd /home/amya/shellscript_practice || exit 1

for folder in a b c d e
do
    sed -i '2d' "$folder"
done
```

**Explanation:**

- `sed` is a stream editor.
- `-i` modifies the original file.
- `2d` deletes the second line.
- The loop processes files a, b, c, d, and e.

---

### Example 4: Search Application Logs Using grep

**Script: `grep.sh`**

```bash
#!/bin/bash

LOG_FILE="application.log"

if [ ! -f "$LOG_FILE" ]; then
    echo "Log file does not exist"
    exit 1
fi

echo "Displaying ERROR messages:"

grep "ERROR" "$LOG_FILE"
```

**Explanation:**

- `grep` searches for matching text.
- `-f` checks whether the path is a regular file.
- `!` negates the condition.
- `exit 1` terminates the script with an error status.

---

### Example 5: Extract Columns Using awk

**Script: `awk.sh`**

```bash
#!/bin/bash

awk '{print $1, $2}' employees.txt
```

**Explanation:**

- `$1` represents the first column.
- `$2` represents the second column.
- `$0` represents the complete row.
- `NR` represents the current record number.
- `NF` represents the number of fields.

**Print the second row:**

```bash
awk 'NR==2' employees.txt
```

**Print the second column of the third row:**

```bash
awk 'NR==3 {print $2}' employees.txt
```

---

## 🚀 How to Execute Shell Scripts

### Step 1: Clone the Repository

```bash
git clone https://github.com/amyadjs-tech/practice-shell-scripting.git
```

### Step 2: Navigate to the Repository

```bash
cd practice-shell-scripting
```

### Step 3: Check Available Files

```bash
ls -lrt
```

### Step 4: Provide Execute Permission

```bash
chmod 755 script.sh
```

Replace `script.sh` with the actual script filename.

### Step 5: Execute the Script

```bash
./script.sh
```

Alternatively:

```bash
bash script.sh
```

---

## 🔍 Shell Script Debugging

### Check Script Syntax

```bash
bash -n script.sh
```

### Debug Script Execution

```bash
bash -x script.sh
```

### Check Exit Status

```bash
echo $?
```

**Exit Status:**

- `0` - Success
- `1` - General error
- `126` - Command cannot execute
- `127` - Command not found

---

## 📊 Important Linux Commands

| Command | Description |
|---------|-------------|
| pwd | Print working directory |
| ls | List files and directories |
| cd | Change directory |
| mkdir | Create directory |
| touch | Create empty file |
| cat | Display file contents |
| vi | Open text editor |
| chmod | Change file permissions |
| grep | Search text patterns |
| awk | Process text and columns |
| sed | Edit and transform text |
| find | Search files and directories |
| ps | Display running processes |
| top | Monitor system processes |
| df -h | Display disk usage |
| free -h | Display memory usage |
| crontab | Schedule automated tasks |

---

## 🎯 Real-World Production Support Use Cases

Shell scripting is widely used in Application Support, Production Support, Linux Administration, and DevOps.

### Application Monitoring
- Monitor application logs.
- Identify ERROR and WARN messages.
- Check application availability.
- Verify application processes.

### System Monitoring
- Monitor CPU utilization.
- Monitor memory usage.
- Check disk space.
- Identify high resource consumption.

### Automation
- Automate repetitive Linux tasks.
- Schedule jobs using cron.
- Automate application health checks.
- Generate log analysis reports.
- Perform file backup operations.

### DevOps
- Automate Docker operations.
- Execute Git commands.
- Support CI/CD pipelines.
- Automate application deployments.
- Perform Kubernetes health checks.

---

## 📈 Learning Roadmap

- [ ] Linux Fundamentals
- [ ] Bash Basics
- [ ] Variables and Operators
- [ ] Conditional Statements
- [ ] Loops
- [ ] Functions
- [ ] File Handling
- [ ] grep
- [ ] awk
- [ ] sed
- [ ] Regular Expressions
- [ ] Error Handling
- [ ] Shell Script Debugging
- [ ] Cron Jobs
- [ ] Application Log Monitoring
- [ ] System Monitoring
- [ ] Docker Automation
- [ ] DevOps Automation Projects

This checklist will be updated as the learning progresses.

---

## 📖 Learning Resources

- [GNU Bash Manual](https://www.gnu.org/software/bash/manual/)
- [GNU grep Manual](https://www.gnu.org/software/grep/manual/)
- [GNU awk Manual](https://www.gnu.org/software/gawk/manual/)
- [GNU sed Manual](https://www.gnu.org/software/sed/manual/)

---

## 👨‍💻 Author

**Amya Prakash Behera**

GitHub: [amyadjs-tech](https://github.com/amyadjs-tech)

Repository: [practice-shell-scripting](https://github.com/amyadjs-tech/practice-shell-scripting)

---

## ⭐ Repository Objective

The objective of this repository is to build strong practical knowledge of Bash Shell Scripting and apply it to:

- Linux Administration
- Application Support
- Production Support
- Troubleshooting
- Automation
- DevOps Engineering

**Learning Bash Shell Scripting through hands-on practice and real-world scenarios.**

---

⭐ If you find this repository useful, consider giving it a star!

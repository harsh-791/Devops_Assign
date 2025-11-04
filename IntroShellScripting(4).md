# Introduction to Shell Scripting & Linux Basics DevOps — Class 4 


## 1. Topics Covered

* Linux commands and file operations
* File permissions and `chmod`
* `find` and `locate`
* ACL (Access Control Lists)
* `vi` editor
* Shell scripting basics
* Shebang (`#!`)
* Script structure
* Variables and arguments
* Conditional statements
* File checks
* String manipulation
* User and group management
* Script headers and best practices
* Error handling and input validation
* Root privilege checking

---

## 2. Linux Commands & File Operations

```bash
pwd
cd
ls
mkdir
rmdir
rm
```

```bash
rm -rf foldername
```

---

## 3. File Permissions & chmod

Permission types:

* r → read
* w → write
* x → execute

```bash
chmod 755 script.sh
chmod u+x script.sh
```

Permission sets:

* User
* Group
* Others

---

## 4. find & locate

```bash
find / -name file.txt
locate file.txt
```

* `find` → real-time search
* `locate` → indexed search

---

## 5. ACL (Access Control Lists)

```bash
getfacl file.txt
setfacl -m u:username:rwx file.txt
```

---

## 6. vi Editor

Modes:

* Command mode
* Insert mode

Basic commands:

```bash
i
Esc
:w
:q
:wq
:q!
```

---

## 7. Shell Scripting Basics

A shell script is a file containing Linux commands executed in sequence.

---

## 8. Shebang (#!)

```bash
#!/bin/bash
```

---

## 9. Basic Script Structure

```bash
#!/bin/bash

# Author:
# Version:
# Description:

echo "Hello World"
```

---

## 10. Variables & Arguments

```bash
name="value"
echo $name
```

```bash
echo $1
echo $2
echo $#
```

---

## 11. Conditional Statements

```bash
if [ condition ]; then
    commands
else
    commands
fi
```

---

## 12. File Checking Operations

```bash
-f file
-d dir
-r file
-w file
-x file
```

---

## 13. String Manipulation

```bash
name="harsh"
echo ${name^^}
```

---

## 14. User & Group Management

```bash
useradd username
groupadd groupname
```

---

## 15. Script Header & Best Practices

* Add header comments
* Validate inputs
* Handle errors
* Use proper exit codes
* Do not assume root access

---

## 16. Error Handling & Input Validation

```bash
if [ $# -ne 1 ]; then
    echo "Usage: ./script.sh filename"
    exit 1
fi
```

---

## 17. Root Privilege Check

```bash
if [ $EUID -ne 0 ]; then
    echo "Please run as root"
    exit 1
fi
```

---

## 18. Important Points

* Shebang
* chmod
* vi modes
* `$1`, `$2`, `$#`
* if-else
* File test operators
* `$EUID`
* Script structure

---

## 19. Summary

* Linux commands are the base of automation
* Shell scripts are used for task automation
* Always validate inputs
* Always follow proper script structure
* Check permissions when needed

---
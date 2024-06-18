# Bash Scripting

---

## 1. General Commands

### 1.1. cd

Changes the current directory.

```sh
cd /home/user
cd Documents
cd ..
```

### 1.2. ls

Lists the contents of a directory.

```sh
ls
ls -l
ls /home/user/Documents
```

### 1.3. pwd

Shows the full path of the current directory.

```sh
pwd
```

### 1.4. mkdir

Creates a new directory.

```sh
mkdir new_directory
mkdir -p parent_directory/child_directory
```

### 1.5. rmdir

Deletes an empty directory.

```sh
rmdir empty_directory
```

### 1.6. rm

Removes files or directories.

```sh
rm file.txt
rm -r directory_to_remove
rm -f force_remove_file.txt
```

### 1.7. cp

Copies files or directories.

```sh
cp source_file.txt destination_file.txt
cp -r source_directory/ destination_directory/
```

### 1.8. mv

Moves or renames files or directories.

```sh
mv old_name.txt new_name.txt
mv /path/to/file /new/path/
```

### 1.9. touch

Creates an empty file or updates the timestamp of an existing file.

```sh
touch newfile.txt
touch existingfile.txt
```

### 1.10. cat

Displays the content of a file.

```sh
cat file.txt
cat file1.txt file2.txt > combined.txt
```

### 1.11. nano

Edits files using the nano text editor.

```sh
nano file.txt
```

### 1.12. vim

Edits files using the vim text editor.

```sh
vim file.txt
```

### 1.13. echo

Prints a message or a variable's value.

```sh
echo "Hello, World!"
echo $PATH
```

### 1.14. chmod

Changes the permissions of a file or directory.

```sh
chmod 755 script.sh
chmod +x script.sh
```

### 1.15. chown

Changes the owner of a file or directory.

```sh
chown user:group file.txt
sudo chown root:root /etc/important_file
```

### 1.16. grep

Searches for text within files.

```sh
grep "search_term" file.txt
grep -r "search_term" /path/to/directory
```

### 1.17. find

Finds files and directories.

```sh
find /path/to/search -name "*.txt"
find . -type f -name "file.txt"
```

### 1.18. df

Shows available disk space.

```sh
df -h
df /home
```

### 1.19. du

Shows disk usage by files or directories.

```sh
du -sh /path/to/directory
du -h --max-depth=1
```

### 1.20. tar

Archives files into a single tar file.

```sh
tar -cvf archive.tar /path/to/directory
tar -xvf archive.tar
```

### 1.21. gzip

Compresses files using gzip.

```sh
gzip file.txt
gzip -d file.txt.gz
```

### 1.22. gunzip

Decompresses gzip files.

```sh
gunzip file.txt.gz
```

### 1.23. ps

Shows running processes.

```sh
ps aux
ps -ef
```

### 1.24. kill

Sends a signal to stop a process.

```sh
kill 1234
kill -9 1234
```

### 1.25. man

Shows the manual for a command.

```sh
man ls
man grep
```

### 1.26. ssh

Connects to a remote host via SSH.

```sh
ssh user@hostname
```

### 1.27. wget

Downloads files from the web.

```sh
wget http://example.com/file.zip
wget -O custom_name.zip http://example.com/file.zip
```

### 1.28. history

Shows the command history.

```sh
history
history | grep "search_term"
```

### 1.29. sudo

Runs a command as the superuser.

```sh
sudo apt-get update
sudo nano /etc/hosts
```

### 1.30. apt-get

Manages software packages (install, update, remove).

```sh
sudo apt-get update
sudo apt-get install package_name
sudo apt-get remove package_name
```

### 1.31. exit

Closes the current shell session.

```sh
exit
```

### 1.32. reboot

Restarts the system.

```sh
sudo reboot
```

### 1.33. shutdown

Shuts down or restarts the system after a specified time.

```sh
sudo shutdown -h now
sudo shutdown -r now
sudo shutdown -h +10 "System will shutdown in 10 minutes"
```

## 2. Shell scripting

### 2.1. Hello World Script

Prints "Hello, World!" to the terminal.

```sh
#!/bin/bash
echo "Hello, World!"
```

### 2.2. Variables

Declares and uses variables.

```sh
#!/bin/bash
name="Alice"
echo "Hello, $name"
```

### 2.3. User Input

Reads user input.

```sh
#!/bin/bash
echo "Enter your name:"
read name
echo "Hello, $name"
```

### 2.4. If Statement

Uses conditions to execute code blocks.

```sh
#!/bin/bash
echo "Enter a number:"
read number
if [ $number -gt 10 ]; then
  echo "The number is greater than 10"
else
  echo "The number is 10 or less"
fi
```

### 2.5. For Loop

Repeats code for a list of values.

```sh
#!/bin/bash
for i in 1 2 3 4 5
do
  echo "Number: $i"
done
```

### 2.6. While Loop

Repeats code while a condition is true.

```sh
#!/bin/bash
count=1
while [ $count -le 5 ]
do
  echo "Count: $count"
  ((count++))
done
```

### 2.7. Functions

Declares and calls functions.

```sh
#!/bin/bash
greet() {
  echo "Hello, $1"
}
greet "Alice"
greet "Bob"
```

### 2.8. Command Substitution

Uses the output of a command in a variable.

```sh
#!/bin/bash
current_date=$(date)
echo "Today's date is: $current_date"
```

### 2.9. String Manipulation

Extracts a substring from a string.

```sh
#!/bin/bash
str="Hello, World!"
echo ${str:7:5}
```

### 2.10. File Test Operators

Checks if a file exists.

```sh
#!/bin/bash
file="test.txt"
if [ -e $file ]; then
  echo "$file exists"
else
  echo "$file does not exist"
fi
```

### 2.11. Basic Arithmetic

Performs simple arithmetic operations.

```sh
#!/bin/bash
num1=5
num2=3
sum=$((num1 + num2))
echo "Sum is: $sum"
```

### 2.12. Reading a File Line by Line

Reads a file line by line and prints each line.

```sh
#!/bin/bash
while IFS= read -r line
do
  echo "$line"
done < "file.txt"
```

### 2.13. Case Statement

Uses a case statement for multiple selections.

```sh
#!/bin/bash
echo "Enter a number between 1 and 3:"
read number
case $number in
  1)
    echo "You entered one"
    ;;
  2)
    echo "You entered two"
    ;;
  3)
    echo "You entered three"
    ;;
  *)
    echo "Invalid number"
    ;;
esac
```

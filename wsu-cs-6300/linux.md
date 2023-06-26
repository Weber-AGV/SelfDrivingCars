---
sort: 1
---

# Linux

## Linux Shell

# Common Linux Terminal Commands

Here are some common terminal commands for Linux systems.

## Navigation Commands

- `ls`: List files and directories in the current directory.
- `cd [dir]`: Change the current directory to the directory specified. For example, `cd /home/user` would change the current directory to `/home/user`.
- `pwd`: Print the path of the current working directory.

## File and Directory Operations

- `cp [source] [destination]`: Copy a file or directory from the source to the destination.
- `mv [source] [destination]`: Move a file or directory from the source to the destination.
- `rm [file]`: Remove a file. Be careful with this command, as it permanently deletes files.
- `mkdir [dir]`: Create a new directory.

## System Information

- `uname -a`: Display all system information.
- `df -h`: Display disk space usage in human-readable format.
- `free -h`: Display free and used memory in the system in human-readable format.

## Process and Job Control

- `ps`: List the currently running processes.
- `top`: Display the system's running processes in real-time.
- `kill [PID]`: Kill a process with a specific PID (Process ID).

## Network Commands

- `ping [host]`: Send a network request to a specific host to check if it is up and running.
- `ifconfig` or `ip addr`: Display or configure a network interface.
- `netstat`: Network Statistics.

## File Permissions

- `chmod [permissions] [file]`: Change the file system permissions of files and directories.
- `chown [user]:[group] [file]`: Change the user and group ownership of files and directories.

## Searching and Sorting

- `grep [pattern] [file]`: Search for a specific pattern within a file.
- `sort`: Sort lines in text files.
- `find [dir] -name [file]`: Find files inside a directory.

## Compression and Archiving

- `tar -cvf [file.tar] [file or dir]`: Archive files or directories.
- `tar -xvf [file.tar]`: Extract files or directories from an archive.
- `gzip [file]`: Compress a file to a .gz archive.
- `gunzip [file.gz]`: Decompress a .gz archive.

Please note that you should replace `[...]` with your specific arguments.


## chmod - details - File Permissions using chmod

- `chmod [permissions] [file]`: Change the file system permissions of files and directories. 

Permissions are defined as a three-digit number where each digit is an octal number that represents the permissions for the owner, group, and others respectively. Each octal number is the sum of read (4), write (2), and execute (1) permissions. For example, `chmod 755 [file]` would give the owner read, write, and execute permissions (7), and the group and others only read and execute permissions (5). 

Here is what each of these means:

- Read (4): The file can be opened, and its content viewed.
- Write (2): The file can be edited, modified, and deleted.
- Execute (1): If the file is a script or a program, it can be run (executed).

For directories, the permissions have slightly different meanings:

- Read (4): The directory listing can be obtained.
- Write (2): Items within the directory can be created, deleted, and renamed if execute permission is also set.
- Execute (1): The directory can be entered (i.e., `cd [dir]`).

To apply these permissions:

- For the user who owns the file/directory (`u`):
- For other users in the file's group (`g`):
- For other users not in the file's group (`o`):
- For all users (`a`):

You can use the format `ugoa` (where `u` = user, `g` = group, `o` = others, `a` = all) combined with `+-=` (where `+` = add a permission, `-` = remove a permission, `=` = set exactly these permissions) and `rwx` (where `r` = read, `w` = write, `x` = execute). 

For example:

- `chmod u+x [file]`: This would add (`+`) execute (`x`) permission for the user (`u`) who owns the file or directory.
- `chmod go-rw [file]`: This would remove (`-`) both read (`r`) and write (`w`) permissions for other users in the file's group (`g`) and for other users not in the file's group (`o`).

Be careful while using this command and make sure you know exactly what permissions you are setting.


---
share: true
---
# Comprehensive UNIX Cheatsheet

## Basic Unix Commands for File Navigation, Manipulation, and Text Processing

- `ls`: List files and directories in the current directory.
- `ls -l`: List files with detailed information.
- `cd [directory]`: Change the current directory.
- `pwd`: Print the current working directory.
- `cat [file]`: Display the contents of a file.
- `more [file]`: Display file contents one screen at a time.
- `less [file]`: View and navigate file contents interactively.
- `head [file]`: Display the first few lines of a file.
- `tail [file]`: Display the last few lines of a file.
- `echo [text]`: Print text to the terminal.
- `mv [source] [destination]`: Move or rename a file or directory.
- `cp [source] [destination]`: Copy files or directories.
- `rm [file]`: Remove a file.
- `mkdir [directory]`: Create a new directory.
- `rmdir [directory]`: Remove an empty directory.
- `touch [file]`: Create an empty file.
- `grep [pattern] [file]`: Search for a pattern in a file.
- `sed 's/find/replace/' [file]`: Stream editor for text manipulation.
- `sort [file]`: Sort lines of text in a file.
- `wc [file]`: Count lines, words, and characters in a file.

## Working with Files and Directories

- `chmod [permissions] [file]`: Change file permissions.
- `chown [user]:[group] [file]`: Change file ownership.
- `chgrp [group] [file]`: Change group ownership of a file.
- `find [directory] -name [filename]`: Search for files by name.
- `find [directory] -type [f/d]`: Search for files (f) or directories (d).
- `tar -cvf [archive.tar] [file/dir]`: Create a tar archive.
- `tar -xvf [archive.tar]`: Extract files from a tar archive.
- `zip -r [archive.zip] [file/dir]`: Create a zip archive.
- `unzip [archive.zip]`: Extract files from a zip archive.

## Shell Scripting: Creating and Executing Shell Scripts

- Create a new shell script: `touch script.sh`
- Add script content using a text editor (e.g., `nano`, `vim`).
- Make the script executable: `chmod +x script.sh`
- Execute the script: `./script.sh`

## File Permissions and User Management

- `whoami`: Display the current username.
- `id [username]`: Display user and group information.
- `passwd [username]`: Change the user password.
- `sudo [command]`: Execute a command with superuser privileges.
- `su [username]`: Switch to another user.
- `useradd [username]`: Create a new user.
- `usermod [options] [username]`: Modify user properties.
- `userdel [username]`: Delete a user.
- `groupadd [groupname]`: Create a new group.
- `groupmod [options] [groupname]`: Modify group properties.
- `groupdel [groupname]`: Delete a group.

## Using Pipes and Redirects for Data Manipulation

- `command1 | command2`: Pipe the output of command1 to command2.
- `command > file`: Redirect command output to a file (overwrite).
- `command >> file`: Append command output to a file.
- `command < file`: Provide file content as input to a command.
- `command 2> error.log`: Redirect error output to a file.
- `command1 && command2`: Execute command2 only if command1 succeeds.
- `command1 || command2`: Execute command2 only if command1 fails.


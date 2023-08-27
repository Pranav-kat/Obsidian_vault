---
share: true
---

# Comprehensive UNIX Cheatsheet

## Basic Unix Commands for File Navigation, Manipulation, and Text Processing

- `ls`: List files and directories.
- `ls -l`: List with details.
- `ls -a`: List including hidden files.
- `ls -lh`: List with details in human-readable sizes.
- `cd [directory]`: Change directory.
- `pwd`: Print working directory.
- `cp [source] [destination]`: Copy files/directories.
- `mv [source] [destination]`: Move files/directories.
- `rm [file]`: Remove file.
- `rm -r [directory]`: Remove directory.
- `mkdir [directory]`: Create directory.
- `touch [file]`: Create empty file.
- `cat [file]`: Display file contents.
- `head [file]`: Display first lines.
- `tail [file]`: Display last lines.
- `more [file]`: Display text page by page.
- `less [file]`: Interactive text viewer.
- `grep [pattern] [file]`: Search for pattern.
- `sed 's/find/replace/' [file]`: Text substitution.
- `sort [file]`: Sort lines.
- `uniq [file]`: Remove duplicate lines.
- `wc [file]`: Word, line, character count.

## Working with Files and Directories

- `find [dir] -name [pattern]`: Search for files/dirs.
- `find [dir] -type [f/d]`: Search files (f) or dirs (d).
- `du -h [dir]`: Disk usage.
- `df -h`: Disk space usage.
- `file [file]`: File type information.
- `ln -s [target] [link]`: Create symbolic link.
- `file [file]`: Determine file type.
- `which [command]`: Show command path.
- `whereis [command]`: Show command location.
- `locate [file]`: Search for files (index-based).
- `stat [file]`: Display file status.

## File Permissions and Ownership

- `chmod [permissions] [file]`: Change file permissions.
- `chown [user]:[group] [file]`: Change ownership.
- `umask [mask]`: Set default permissions.
- `passwd [user]`: Change user password.
- `su [user]`: Switch user.
- `sudo [command]`: Execute with superuser privileges.
- `/etc/passwd`: User account info.
- `/etc/group`: Group info.
- `/etc/shadow`: Encrypted passwords.
- `id [user]`: User and group info.

## Processes and System Monitoring

- `ps`: List processes.
- `ps aux`: List all processes.
- `top`: Interactive process viewer.
- `htop`: Enhanced top.
- `kill [PID]`: Terminate process.
- `killall [process]`: Terminate all processes.
- `nice [command]`: Set process priority.
- `renice [priority] [PID]`: Change process priority.
- `uptime`: System uptime.
- `free -h`: Memory usage.
- `df -h`: Disk space usage.
- `netstat`: Network statistics.
- `ifconfig`: Network interface info.

## Shell Scripting and Automation

- `#!/bin/bash`: Shebang for Bash scripts.
- Variables: `$variable`, `${variable}`.
- Conditionals: `if`, `elif`, `else`.
- Loops: `for`, `while`, `until`.
- Functions: `function_name() { ... }`.
- Command substitution: `$(command)`.
- Arithmetic: `((expr))`, `$((expr))`.
- Reading input: `read var`.
- File tests: `-e`, `-d`, `-f`.
- Control operators: `&&`, `||`.
- `case` statement: Multiple condition checks.
- `grep`, `sed`, `awk` usage in scripts.

## Networking and System Administration

- `ifconfig`: Configure network interfaces.
- `ping [host]`: Ping a host.
- `nslookup [domain]`: DNS lookup.
- `ssh [user@]host`: Secure shell.
- `scp [file] [user@]host:[dir]`: Secure copy.
- `rsync [options] [source] [destination]`: Remote sync.
- `netstat -tuln`: List open ports.
- `iptables`: Configure firewall rules.
- `crontab -e`: Edit cron jobs.
- `/etc/crontab`: System-wide cron jobs.
- `hostnamectl`: Display system hostname.
- `systemctl [start/stop/restart/status] [service]`: Systemd service management.

## Input and Output Redirection

- `command > file`: Redirect stdout to file (overwrite).
- `command >> file`: Redirect stdout to file (append).
- `command < file`: Provide file content as input.
- `command 2> file`: Redirect stderr to file (overwrite).
- `command 2>> file`: Redirect stderr to file (append).
- `command &> file`: Redirect both stdout and stderr to file.
- `command1 | command2`: Pipe output of command1 to command2.
- `command > file 2>&1`: Redirect stdout and stderr to file.

## Text Processing and Manipulation

- `sed 's/find/replace/' [file]`: Stream editor.
- `awk '{action}' [file]`: Text processing language.
- `cut -d [delimiter] -f [fields] [file]`: Extract fields.
- `grep [pattern] [file]`: Search for pattern.
- `grep -r [pattern] [dir]`: Recursively search.
- `grep -v [pattern] [file]`: Invert match.
- `grep -i [pattern] [file]`: Case-insensitive search.
- `sort [file]`: Sort lines.
- `sort -n [file]`: Sort numerically.
- `sort -r [file]`: Reverse sort.
- `uniq [file]`: Remove duplicate lines.
- `tr [set1] [set2]`: Translate characters.
- `wc [file]`: Word, line, character count.

## Advanced Text Processing with Regular Expressions

- `grep [regex] [file]`: Search with regex.
- `sed 's/[regex]/replace/' [file]`: Replace with regex.
- `awk '/[regex]/ {action}' [file]`: Action on regex match.
- `egrep [regex] [file]`: Extended regex search.
- `grep -P [regex] [file]`: Perl-compatible regex.
- `grep -o [regex] [file]`: Show only matched parts.
- `grep -A [num] -B [num] [regex] [file]`: Context around match.

## Environment and Shell Variables

- `env`: Display environment variables.
- `echo $VAR`: Print the value of a variable.
- `export VAR=value`: Set environment variable.
- `unset VAR`: Unset environment variable.
- `source [file]` or `. [file]`: Execute script in current shell.
- `history`: Command history.
- `!n`: Repeat the nth command.
- `$_`: Last argument of the last command.
- `CTRL+R`: Reverse search in history.
- `CTRL+A`, `CTRL+E`: Move to beginning/end of line.
- `CTRL+U`, `CTRL+K`: Cut to beginning/end of line.
- `CTRL+W`: Cut word before cursor.

## Miscellaneous

- `date`: Display date and time.
- `cal [month] [year]`: Display calendar.
- `time [command]`: Measure command execution time.
- `alias [name]='[command]'`: Create command alias.
- `which [command]`: Show command path.
- `whereis [command]`: Show command location.
- `man [command]`: Display manual for command.
- `info [command]`: Display info page for command.
- `clear`: Clear the terminal screen.
- `Ctrl+C`: Interrupt current command.
- `Ctrl+D`: Exit shell or end input.
- `Ctrl+Z`: Suspend current command.
- `bg` or `fg`: Background or foreground process.


# Linux cheat sheet

* TOC (placeholder for the automatic creation of a Table of contents)
{:toc}

## Bash shortcuts

> Keys when in emacs mode. You can switch to 'vi' mode with 'set -o vi' command. Be back to emacs mode with 'set -o emacs'.

#### Movements

| Command    | Description                           |
|------------|---------------------------------------|
| Ctrl + a   | Go to beginning of line.              |
| Ctrl + e   | Go to end of line.                     |
| Ctrl + f   | Move forward one character.           |
| Ctrl + b   | Move backwards one character.         |
| Alt + f    | Move forward one word.                |
| Alt + b    | Move backwards one word.              |
{:.shortcuts-table}

#### Editing

| Command                          | Description                                              |
|----------------------------------|----------------------------------------------------------|
| Ctrl + k                         | Delete all characters after cursor.                      |
| Ctrl + u                         | Delete all characters before cursor.                     |
| Ctrl + w **or** Alt + Backspace  | Delete previous word or all characters of the word before cursor. |
| Alt + d                          | Delete next word or all characters of the word after cursor.|
| Ctrl + y                         | Paste previous deleted text.                             |
| Alt + u                          | Capitalize all characters in a word after the cursor.     |
| Alt + l                          | Uncapitalize all characters in a word after the cursor.   |
| Alt + .                          | Paste the last word of the previous executed command.     |
| Ctrl + l                         | Clears the screen and redisplay the line.                 |
| Ctrl + m                         | Enter. In practice same as RETURN.                        |
| Ctrl + j                         | Newline. In practice same as RETURN.                      |
| Ctrl + x, Ctrl + e               | Edit command in editor.                                   |
{:.shortcuts-table}

#### History

| Command    | Description                                              |
|------------|----------------------------------------------------------|
| !n         | Execute nth command in history.                          |
| !n:p       | Put the nth command in history without executing it. Then you can ctr+p and modify it. |
| !!         | Execute previous command.                                 |
| fc [n]     | Edit the nth command in history or the last one if there is no n param. |
| :cq        | Exit vi/vim without executing when editing with fc.      |
| history    | Show history.                                            |
| Ctrl + r   | Search history backward.                                 |
| Ctrl + p   | Fetch the previous command from the history list.         |
| Ctrl + n   | Fetch the next command from the history list.             |
| Ctrl + g   | Escape from history searching mode.                       |
| Ctrl + o   | Run the command found in history mode.                    |
{:.shortcuts-table}

#### Jobs

| Command      | Description                               |
|--------------|-------------------------------------------|
| Ctrl + z     | Suspends current command execution and moves it to the background. |
| jobs         | Prints currently running job              |
| bg <job_id>  | Put job in background                     |
| fg <job_id>  | Bring job to the foreground               |
| %n           | Job number n                              |
| %s           | Job whose command line starts with s      |
| %%           | Current job                               |
| %-           | Previous job                              |
{:.shortcuts-table}


## Users Information and Management

```bash
# Get information about own user and other users
whoami                     # Prints the effective username of the current user.
id                         # Displays user and group information for the current user.
id [username]              # Displays user and group information for a specified user.
finger [username]          # Displays user information, including login name, full name, terminal, idle time, login time, and more.

# Get information about connected users
w                          # Provides a summary of logged-in users.
who                        # Shows who is currently logged in.
last                       # Shows a list of last logged-in users.
lastb                      # View bad login attempts.

# Get information about configured users and groups
cat /etc/passwd | column -t -s ":"    # Displays information about user accounts from /etc/passwd file.
cat /etc/shadow | column -t -s ":"    # Displays information about user passwords in /etc/passwd file.
cut -d: -f1 /etc/passwd               # Extracts and displays a list of usernames from /etc/passwd file.
getent passwd                         # Retrieves user account information, including users from remote databases.
groups                                # Displays the groups to which the current user belongs.
cat /etc/group | column -t -s ":"     # Displays information about groups from /etc/group file.
members [groupname]                   # Lists the members of a specific group.
chage [options] [username]            # Configures the password expiry information for a user.

# Manage users and groups
passwd [username]                      # Allows a user to change their password or allows a superuser to change another user's password.
useradd [options] [username]           # A lower-level command for adding new users to the system.
adduser [options] [username]           # A higher-level user management command that is more user-friendly and interactive.
userdel [username]                     # Remove a user.
userdel --remove [username]            # Remove a user along with the home directory and mail spool.
deluser -remove-all-files [username]   # A higher-level user removal. Removes also files outside home, cron jobs, etc.
usermod [options] [username]           # Modifies a user account.
vipw                                   # Edit password file.
vigr                                   # Edit groups file.
```

## System Information

```bash
# Miscellaneous System Information
uptime                    # Show how long the system has been running.
date                      # Display the current date and time.

# General System Information
uname -a                  # Display system information (kernel version, architecture, etc.).
hostnamectl               # Display system hostname and related information.
lsb_release -a            # Display distribution-specific information.
cat /etc/os-release       # Show information about the operating system.

# System and Hardware Information
lscpu                                                                         # Display information about the CPU architecture.
lshw                                                                          # List hardware details.
hwinfo                                                                        # Display hardware information.
dmidecode; dmidecode -t system; dmidecode -t bios; dmidecode -t processor     # Retrieve hardware information from the system BIOS/UEFI, processor, memory....
lspci                                                                         # Display information about PCI buses and devices.
lsscsi                                                                        # View all your scsi/sata devices. 
lsusb                                                                         # Show information about USB buses and devices.
lsblk                                                                         # List information about block devices.
cat /proc/cpuinfo                                                             # Show CPU detailed information.
sensors                                                                       # Report sensors information. First time requires a 'sensors detect'.
pwmconfig                                                                     # Control fan speed.


# Memory Information
free -h                   # Display memory usage information.
vmstat                    # Report virtual memory statistics.
cat /proc/meminfo         # View detailed information about system memory.

# Disk and Filesystem Information and tests
df -h                     # Display disk space usage.
du -h --max-depth=1       # Show directory sizes in the current location.
fdisk -l                  # Display partition information.
ls -l /dev/disk/by-uuid   # List UUIDs of storage devices.
mount                     # Show all mounted filesystems.
blkid -o list             # List all partitions in a table, including current mountpoints
cat /proc/mounts          # View mounted filesystems. 
hdparm -tT /dev/sdXXXX    # Do a read speed test


# Network Information
ifconfig                  # Show network interface information (deprecated, use 'ip' command).
ip a                      # Display information about network interfaces.
netstat -tuln              # Show listening ports.
cat /etc/resolv.conf      # Display DNS information.
route -n                  # Display routing table.

# Process Information
ps aux                    # Display information about running processes.
top                       # Show real-time system statistics.
htop                      # An interactive process viewer.
btop                      # Another interactive process viewer.
pmap [pid]                # Display memory map of a process.
lsof                      # List open files and processes.

# Kernel Information
dmesg                     # Print kernel ring buffer messages.
uname -r                  # Display the kernel release.

# System Logs
journalctl                # Query and display messages from the journal.


# Environmental Variables
env                       # Display environment variables.
printenv                  # Print environment variables.

# System Configuration Files
cat /etc/hosts            # Display information about network hosts.
cat /etc/fstab            # Show information about file systems and storage.

# System Performance
sar                       # Collect, report, or save system activity information.
iostat                    # Report CPU and I/O statistics.
```

## Files

### GNU Coreutils

| Command | Option | Description                                       |
|---------|--------|---------------------------------------------------|
| **ls**  |        | List directory contents                           |
| ^       | -h     | Human readable                                    | 
| ^       | -a     | List all files, including hidden                  | 
| ^       | -l     | Long format list                                  | 
| ^       | -d     | List directory names instead of contents          | 
| ^       | -S     | Sort by size                                      |
| ^       | -t     | Sort by time                                      |
| ^       | -r     | Reverse order                                     |
| ^       | -s     | Print allocated size of each file in blocks       |
| ^       | -1     | One file per line                                 |
| ^       | ./     | List contents one level deep                      |
| ^       | -i     | Get inode number of file (file id). Use `sudo find / -inum <number>` to find all links that point to the same file.|

| Command | Option | Description                                       |
|---------|--------|---------------------------------------------------|
| **cp**  |        | Copy files or directories                         |
|         | -r     | Copy directories recursively                       | 
|         | -i     | Prompt before overwriting files                    | 
|         | -u     | Copy only when the source file is newer or missing| 
|         | -n     | Do not overwrite existing files                    | 
|         | -a     | Archive mode (preserving ownership and permissions)| 
|         | -l     | Create hard links instead of copying               | 
|         | -s     | Create symbolic links instead of copying           | 
|         | -T     | Treat the destination as a file                     |
|         | -P     | Do not follow symbolic links in source              |
|         | -v     | Verbose mode (showing files as they are copied)    | 

| Command | Option | Description                                       |
|---------|--------|---------------------------------------------------|
| **rm**  |        | Remove files or directories                       |
|         | -r     | Remove directories and their contents recursively | 
|         | -i     | Prompt before every removal                        | 
|         | -f     | Force removal without confirmation                 | 
|         | -u     | Remove only when the file is newer or missing      | 
|         | -l     | Remove symbolic links only                         | 
|         | -d     | Remove empty directories                           | 
|         | -R     | Similar to -r, used for compatibility               |
|         | -P     | Overwrite regular files before deleting             |
|         | -W     | Attempt to undelete the named files                 |
|         | -v     | Verbose mode (showing files as they are removed)   | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **rmdir**|         | Remove empty directories                         |
|         | -p      | Remove parent directories as needed              | 
|         | -v      | Verbose mode (show removed directories)          | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **mkdir** |        | Create directories                                |
|         | -p      | Create parent directories as needed               | 
|         | -m      | Set the file mode (permissions) for the created directory | 
|         | -v      | Verbose mode (display the created directory)       | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **touch**|         | Change file timestamps or create empty files     |
|         | -c      | Do not create the file if it does not exist      | 
|         | -a      | Change only the access time                      | 
|         | -m      | Change only the modification time                  | 
|         | -t      | Set file time to specific value: (YYYYMMDDhhmm.ss) |
|         | -d      | Use a specified date/time                         | 
|         | -r      | Use the timestamp of another file                | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **ln**  |         | Create links to files and directories             |
| *syntax*|         | ln [options] {{path/to/file_or_directory}} {{path/to/symlink}}      |
|         | -s      | Create symbolic links (symlinks)                  | 
|         | -f      | Force. Remove existing destination files          | 
|         | -b      | Make a backup of the existing target file         | 
|         | -i      | Prompt before removing existing destination files | 
|         | -r      | Make relative symbolic links                      | 
|         | -T      | Treat the target as a normal file                  | 
|         | -v      | Verbose mode (show the files as they are processed)| 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **df**  |         | Report file system  disk space usage              |
|         | -h      | Human-readable format (KB, MB, GB)               | 
|         | -T      | Show filesystem type                              | 
|         | -t      | Limit the display to specific filesystem types   | 
|         | -i      | Display inode information                         | 
|         | -k      | Display sizes in kilobytes                        | 
|         | -m      | Display sizes in megabytes                        | 
|         | -P      | Output in POSIX format                            | 
|         | -x      | Exclude specific filesystem types                | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **du**  |         | Display disk usage of files and directories      |
|         | -h      | Human-readable format (KB, MB, GB)               | 
|         | -d      | Specify the depth of the display                 | 
|         | -c      | Display a grand total                             | 
|         | -s      | Display only a total for each argument           | 
|         | -a      | Show all files, not just directories             | 
|         | -k      | Display sizes in kilobytes                        | 
|         | -m      | Display sizes in megabytes                        | 
|         | -g      | Display sizes in gigabytes                        | 
|         | --exclude | Exclude specific directories or files            | 
|         | --max-depth | Print the total for each directory at most N levels deep | 
|         | --time  | Show time of the last modification                | 
|         | --help  | Display help information                           | 
|         | --version| Display version information                        |


### Other Non GNU Coreutils

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **tree**|         | List contents of directories in a tree-like format|
|         | -a      | All files are listed including hidden ones        | 
|         | -L      | Level of depth for directories to show             | 
|         | -d      | List only directories                             | 
|         | -f      | Display the full path prefix                      | 
|         | -i      | Don't print indentation lines                      | 
|         | -p      | Print the protections for each file                | 
|         | -s      | Print the size of each file                        | 
|         | -h      | Print human-readable file sizes                    | 
|         | -u      | Display file modification times                    | 

| Command | Option  | Description                                       |
|---------|---------|---------------------------------------------------|
| **file**|         | Determine file type                               |
|         | -b      | Do not prepend filenames to output               | 
|         | -z      | Look inside a zipped file and determine the file type(s) inside  | 
|         | -L      | Follow symbolic links                             | 
|         | -i      | Determine the MIME encoding type of a file.       |
|         | --help  | Display help information                           | 
|         | --version| Display version information                        |


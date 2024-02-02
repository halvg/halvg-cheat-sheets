# Linux util commands

* TOC (placeholder for the automatic creation of a Table of contents)
{:toc}

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

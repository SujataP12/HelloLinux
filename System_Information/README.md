# System Information Commands

## System Overview
```bash
# System information
uname -a                    # Complete system information
uname -r                    # Kernel version
uname -m                    # Machine architecture
hostnamectl                 # System hostname and info
lsb_release -a             # Ubuntu version information
cat /etc/os-release        # OS release information
```

## Hardware Information
```bash
# CPU Information
lscpu                      # CPU architecture info
cat /proc/cpuinfo          # Detailed CPU information
nproc                      # Number of processing units

# Memory Information
free -h                    # Memory usage (human readable)
cat /proc/meminfo          # Detailed memory information
vmstat                     # Virtual memory statistics

# Disk Information
lsblk                      # List block devices
fdisk -l                   # List disk partitions
df -h                      # Disk space usage
du -h /path                # Directory space usage

# Hardware Devices
lshw                       # List all hardware
lspci                      # PCI devices
lsusb                      # USB devices
lsmod                      # Loaded kernel modules
```

## System Monitoring
```bash
# Process monitoring
top                        # Real-time process viewer
htop                       # Enhanced process viewer
ps aux                     # All running processes
ps -ef                     # Full format process list

# System load
uptime                     # System uptime and load
w                          # Who is logged in and what they're doing
who                        # Currently logged in users
last                       # Login history

# System resources
iostat                     # I/O statistics
sar                        # System activity reporter
vmstat 1                   # Virtual memory stats every second
```

## Network Information
```bash
# Network interfaces
ip addr show               # Show IP addresses
ifconfig                   # Network interface configuration
ip route show              # Routing table
netstat -tuln              # Network connections
ss -tuln                   # Socket statistics
```

## System Logs
```bash
# System logs
journalctl                 # Systemd journal
journalctl -f              # Follow journal in real-time
journalctl -u service_name # Logs for specific service
dmesg                      # Kernel messages
tail -f /var/log/syslog    # Follow system log
```

## Environment Information
```bash
# Environment variables
env                        # All environment variables
echo $PATH                 # PATH variable
echo $HOME                 # Home directory
printenv                   # Print environment

# User information
whoami                     # Current username
id                         # User and group IDs
groups                     # User groups
finger username            # User information
```

## Date and Time
```bash
# Date and time
date                       # Current date and time
timedatectl                # System time settings
cal                        # Calendar
uptime                     # System uptime
```

---
*Author: Sujata*

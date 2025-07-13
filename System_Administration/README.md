# System Administration Commands

## System Control and Management
```bash
# System control
systemctl status                   # System status
systemctl reboot                   # Restart system
systemctl poweroff                 # Shutdown system
systemctl suspend                  # Suspend system
systemctl hibernate                # Hibernate system
shutdown -h now                    # Shutdown immediately
shutdown -r now                    # Restart immediately
shutdown -h +10                    # Shutdown in 10 minutes
```

## Service Management
```bash
# Systemd services
systemctl list-units               # List all units
systemctl list-units --type=service # List services only
systemctl start service_name       # Start service
systemctl stop service_name        # Stop service
systemctl restart service_name     # Restart service
systemctl reload service_name      # Reload service config
systemctl enable service_name      # Enable at boot
systemctl disable service_name     # Disable at boot
systemctl mask service_name        # Mask service
systemctl unmask service_name      # Unmask service
systemctl status service_name      # Service status
systemctl is-active service_name   # Check if active
systemctl is-enabled service_name  # Check if enabled
```

## System Logs and Monitoring
```bash
# Journal logs
journalctl                         # View all logs
journalctl -f                      # Follow logs in real-time
journalctl -u service_name         # Logs for specific service
journalctl --since "1 hour ago"    # Recent logs
journalctl --until "2023-12-01"    # Logs until date
journalctl -p err                  # Error level logs only
journalctl --disk-usage            # Journal disk usage
journalctl --vacuum-time=2weeks    # Clean old logs

# System logs
tail -f /var/log/syslog            # Follow system log
tail -f /var/log/auth.log          # Authentication logs
tail -f /var/log/kern.log          # Kernel logs
dmesg                              # Kernel ring buffer
dmesg -w                           # Watch kernel messages
```

## Disk and Filesystem Management
```bash
# Disk usage
df -h                              # Disk space usage
du -h /path                        # Directory space usage
du -sh /path                       # Summary of directory size
ncdu /path                         # Interactive disk usage

# Filesystem operations
mount /dev/sdb1 /mnt/usb          # Mount filesystem
umount /mnt/usb                   # Unmount filesystem
mount -a                          # Mount all in /etc/fstab
findmnt                           # Show mounted filesystems
lsblk                             # List block devices
blkid                             # Show block device attributes

# Filesystem check and repair
fsck /dev/sdb1                    # Check filesystem
fsck -y /dev/sdb1                 # Auto-repair filesystem
e2fsck /dev/sdb1                  # Check ext2/3/4 filesystem
```

## Process and Resource Management
```bash
# System resources
free -h                           # Memory usage
cat /proc/meminfo                 # Detailed memory info
cat /proc/cpuinfo                 # CPU information
lscpu                             # CPU architecture
uptime                            # System uptime and load
vmstat 1                          # Virtual memory stats
iostat 1                          # I/O statistics
sar -u 1                          # CPU usage statistics
```

## Cron and Task Scheduling
```bash
# Cron management
crontab -e                        # Edit user crontab
crontab -l                        # List user crontab
crontab -r                        # Remove user crontab
crontab -u user -e                # Edit another user's crontab
systemctl status cron             # Check cron service

# System cron files
/etc/crontab                      # System crontab
/etc/cron.d/                      # System cron directory
/etc/cron.daily/                  # Daily cron scripts
/etc/cron.weekly/                 # Weekly cron scripts
/etc/cron.monthly/                # Monthly cron scripts
```

## System Configuration
```bash
# Hostname management
hostnamectl                       # Show hostname info
hostnamectl set-hostname newname  # Set hostname
hostname                          # Show current hostname

# Time and date
timedatectl                       # Show time settings
timedatectl set-timezone UTC      # Set timezone
timedatectl set-ntp true          # Enable NTP
date                              # Show current date/time
hwclock                           # Hardware clock
```

## User and Permission Management
```bash
# System users
cat /etc/passwd                   # User accounts
cat /etc/group                    # Group information
getent passwd                     # All user accounts
getent group                      # All groups
who                               # Currently logged in users
w                                 # Detailed user activity
last                              # Login history
```

## System Security
```bash
# Firewall management
ufw status                        # UFW firewall status
ufw enable                        # Enable firewall
ufw disable                       # Disable firewall
iptables -L                       # List iptables rules

# System updates
apt update && apt upgrade         # Update system packages
apt autoremove                    # Remove unused packages
apt autoclean                     # Clean package cache
unattended-upgrades               # Automatic security updates
```

## System Information and Hardware
```bash
# Hardware information
lshw                              # List hardware
lshw -short                       # Short hardware list
lspci                             # PCI devices
lsusb                             # USB devices
lsmod                             # Loaded kernel modules
modinfo module_name               # Module information
dmesg | grep -i error             # Hardware errors
```

## Environment and Variables
```bash
# Environment management
env                               # Show environment variables
export VAR=value                  # Set environment variable
unset VAR                         # Unset variable
echo $PATH                        # Show PATH variable
which command                     # Find command location
type command                      # Command type information
```

## System Backup and Recovery
```bash
# System backup
rsync -av /home/ /backup/home/    # Backup home directories
tar -czf system-backup.tar.gz /etc /home /var  # System backup
dd if=/dev/sda of=/backup/disk.img # Disk image backup

# System recovery
mount -o remount,rw /             # Remount root as read-write
fsck -y /dev/sda1                 # Repair filesystem
```

## Performance Tuning
```bash
# System performance
sysctl -a                         # All kernel parameters
sysctl vm.swappiness              # Check swap usage
sysctl -w vm.swappiness=10        # Set swap usage
echo 3 > /proc/sys/vm/drop_caches # Clear cache
```

---
*Author: Sujata*

# Process Management Commands

## Process Viewing and Monitoring
```bash
# List processes
ps                         # Current user processes
ps aux                     # All processes with details
ps -ef                     # Full format listing
ps -u username             # Processes for specific user
pstree                     # Process tree view

# Real-time monitoring
top                        # Interactive process viewer
htop                       # Enhanced interactive viewer
atop                       # Advanced system monitor
```

## Process Control
```bash
# Start processes
command &                  # Run command in background
nohup command &            # Run command immune to hangups
screen command             # Run in screen session
tmux                       # Terminal multiplexer

# Process signals
kill PID                   # Terminate process (SIGTERM)
kill -9 PID                # Force kill process (SIGKILL)
kill -STOP PID             # Stop process
kill -CONT PID             # Continue stopped process
killall process_name       # Kill all processes by name
pkill pattern              # Kill processes matching pattern
```

## Job Control
```bash
# Job management
jobs                       # List active jobs
bg                         # Put job in background
fg                         # Bring job to foreground
fg %1                      # Bring job 1 to foreground
Ctrl+Z                     # Suspend current job
Ctrl+C                     # Interrupt current job

# Job scheduling
at now + 5 minutes         # Schedule job
at 14:30                   # Schedule job at specific time
crontab -e                 # Edit cron jobs
crontab -l                 # List cron jobs
```

## System Services (systemd)
```bash
# Service management
systemctl start service_name    # Start service
systemctl stop service_name     # Stop service
systemctl restart service_name  # Restart service
systemctl reload service_name   # Reload service config
systemctl enable service_name   # Enable service at boot
systemctl disable service_name  # Disable service at boot

# Service status
systemctl status service_name   # Service status
systemctl is-active service_name # Check if active
systemctl is-enabled service_name # Check if enabled
systemctl list-units           # List all units
systemctl list-units --failed  # List failed units
```

## Process Priority
```bash
# Process priority
nice -n 10 command         # Start with lower priority
renice 10 PID              # Change priority of running process
ionice -c 3 PID            # Set I/O priority
```

## Process Information
```bash
# Detailed process info
pgrep process_name         # Find process ID by name
pidof process_name         # Get PID of process
lsof                       # List open files
lsof -p PID                # Files opened by specific process
lsof -i :port              # Processes using specific port
fuser -v file              # Processes using file
```

## Memory and CPU Usage
```bash
# Resource usage
pmap PID                   # Memory map of process
cat /proc/PID/status       # Process status information
cat /proc/PID/cmdline      # Command line of process
strace -p PID              # Trace system calls
ltrace -p PID              # Trace library calls
```

## Background Processes and Daemons
```bash
# Daemon management
service service_name start     # Start service (SysV)
service service_name stop      # Stop service (SysV)
service service_name status    # Check service status
update-rc.d service_name enable # Enable service at boot
```

---
*Author: Sujata*

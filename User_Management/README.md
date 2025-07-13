# User Management Commands

## User Account Management
```bash
# Create users
useradd username                   # Create user with defaults
useradd -m username                # Create user with home directory
useradd -m -s /bin/bash username   # Create user with specific shell
useradd -m -G group1,group2 username # Create user with groups
adduser username                   # Interactive user creation (Debian/Ubuntu)

# Modify users
usermod -l newname oldname         # Change username
usermod -d /new/home username      # Change home directory
usermod -s /bin/zsh username       # Change shell
usermod -G group1,group2 username  # Set user groups
usermod -a -G group username       # Add user to group
usermod -L username                # Lock user account
usermod -U username                # Unlock user account

# Delete users
userdel username                   # Delete user (keep home)
userdel -r username                # Delete user and home directory
deluser username                   # Delete user (Debian/Ubuntu)
```

## Password Management
```bash
# Password operations
passwd                             # Change own password
passwd username                    # Change user password (as root)
passwd -l username                 # Lock user password
passwd -u username                 # Unlock user password
passwd -d username                 # Delete user password
passwd -e username                 # Expire user password

# Password policies
chage -l username                  # Show password aging info
chage -M 90 username               # Set password max age
chage -m 7 username                # Set password min age
chage -W 7 username                # Set password warning period
chage -E 2024-12-31 username       # Set account expiry date
```

## Group Management
```bash
# Create and manage groups
groupadd groupname                 # Create group
groupadd -g 1001 groupname         # Create group with specific GID
groupmod -n newname oldname        # Rename group
groupdel groupname                 # Delete group
addgroup groupname                 # Create group (Debian/Ubuntu)
delgroup groupname                 # Delete group (Debian/Ubuntu)

# Group membership
gpasswd -a username groupname      # Add user to group
gpasswd -d username groupname      # Remove user from group
gpasswd -A username groupname      # Make user group admin
newgrp groupname                   # Switch to group
```

## User Information
```bash
# User details
id                                 # Current user ID and groups
id username                        # Specific user ID and groups
whoami                             # Current username
who                                # Currently logged in users
w                                  # Detailed user activity
last                               # Login history
lastlog                            # Last login for all users
finger username                    # User information
getent passwd username             # User account info from database
```

## User Environment
```bash
# Switch users
su username                        # Switch to user
su - username                      # Switch with user environment
sudo command                       # Execute as another user
sudo -u username command           # Execute as specific user
sudo -i                            # Interactive root shell
sudo -s                            # Shell as root

# User sessions
screen                             # Start screen session
tmux                               # Start tmux session
logout                             # Log out current session
exit                               # Exit current shell
```

## File Permissions and Ownership
```bash
# Change ownership
chown user:group file              # Change owner and group
chown user file                    # Change owner only
chgrp group file                   # Change group only
chown -R user:group directory      # Recursive ownership change

# File permissions
chmod 755 file                     # Set permissions (octal)
chmod u+rwx,g+rx,o+rx file        # Set permissions (symbolic)
chmod +x script.sh                 # Add execute permission
chmod -w file                      # Remove write permission
umask 022                          # Set default permissions mask
```

## User Configuration Files
```bash
# Important user files
/etc/passwd                        # User account information
/etc/shadow                        # Encrypted passwords
/etc/group                         # Group information
/etc/gshadow                       # Group passwords
/etc/sudoers                       # Sudo configuration
/etc/login.defs                    # Login defaults
/etc/skel/                         # Default user files
~/.bashrc                          # User bash configuration
~/.profile                         # User profile
~/.bash_profile                    # Bash login profile
```

## User Limits and Quotas
```bash
# User limits
ulimit -a                          # Show all limits
ulimit -n 1024                     # Set file descriptor limit
ulimit -u 100                      # Set process limit
/etc/security/limits.conf          # System limits configuration

# Disk quotas (if enabled)
quota username                     # Show user quota
edquota username                   # Edit user quota
repquota -a                        # Report all quotas
quotaon /dev/sda1                  # Enable quotas
quotaoff /dev/sda1                 # Disable quotas
```

## SSH Key Management
```bash
# SSH keys
ssh-keygen -t rsa                  # Generate RSA key pair
ssh-keygen -t ed25519              # Generate Ed25519 key pair
ssh-copy-id user@hostname          # Copy public key to remote
ssh-add ~/.ssh/private_key         # Add key to SSH agent
ssh-agent bash                     # Start SSH agent
```

## User Monitoring
```bash
# User activity
ac -p                              # Show user connect time
ac username                        # Show specific user time
lastcomm username                  # Show user commands (if accounting enabled)
```

---
*Author: Sujata*

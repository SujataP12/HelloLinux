# Package Management Commands (APT)

## Basic Package Operations
```bash
# Update package lists
apt update                 # Update package database
apt upgrade                # Upgrade all packages
apt full-upgrade           # Upgrade with dependency resolution
apt dist-upgrade           # Distribution upgrade (deprecated)

# Install packages
apt install package_name           # Install single package
apt install package1 package2     # Install multiple packages
apt install ./package.deb          # Install local .deb file
apt reinstall package_name         # Reinstall package
```

## Package Removal
```bash
# Remove packages
apt remove package_name            # Remove package (keep config)
apt purge package_name             # Remove package and config
apt autoremove                     # Remove unused dependencies
apt autoremove --purge             # Remove unused deps and configs
apt autoclean                      # Clean package cache
apt clean                          # Clean entire package cache
```

## Package Information
```bash
# Search and information
apt search keyword                 # Search for packages
apt show package_name              # Show package details
apt list                          # List all packages
apt list --installed              # List installed packages
apt list --upgradable             # List upgradable packages
dpkg -l                           # List installed packages (detailed)
dpkg -l | grep package_name       # Search installed packages
```

## Package Dependencies
```bash
# Dependency management
apt depends package_name           # Show dependencies
apt rdepends package_name          # Show reverse dependencies
apt-cache policy package_name      # Show package policy
apt-mark hold package_name         # Hold package from upgrade
apt-mark unhold package_name       # Remove hold
apt-mark showhold                  # Show held packages
```

## Repository Management
```bash
# Repository operations
add-apt-repository ppa:user/repo   # Add PPA repository
add-apt-repository --remove ppa:user/repo  # Remove PPA
apt-key add keyfile                # Add repository key
apt-key list                       # List repository keys
apt-key del keyid                  # Remove repository key

# Repository files
/etc/apt/sources.list              # Main repository file
/etc/apt/sources.list.d/           # Additional repository files
```

## Advanced Package Operations
```bash
# Package building and source
apt source package_name            # Download source code
apt build-dep package_name         # Install build dependencies
dpkg-buildpackage                  # Build package from source

# Package file operations
dpkg -i package.deb                # Install .deb file
dpkg -r package_name               # Remove package
dpkg -P package_name               # Purge package
dpkg --configure -a                # Configure all packages
dpkg --configure package_name      # Configure specific package
```

## Package Information and Files
```bash
# Package contents
dpkg -L package_name               # List files in package
dpkg -S /path/to/file              # Find package containing file
apt-file search filename           # Search files in all packages
apt-file list package_name         # List files in package

# Package status
dpkg -s package_name               # Package status
apt policy package_name            # Package policy and versions
```

## Snap Package Management
```bash
# Snap operations
snap list                          # List installed snaps
snap find package_name             # Search for snaps
snap install package_name          # Install snap package
snap remove package_name           # Remove snap package
snap refresh                       # Update all snaps
snap refresh package_name          # Update specific snap
snap info package_name             # Show snap information
```

## Flatpak Package Management
```bash
# Flatpak operations
flatpak list                       # List installed flatpaks
flatpak search package_name        # Search for flatpaks
flatpak install package_name       # Install flatpak
flatpak uninstall package_name     # Remove flatpak
flatpak update                     # Update all flatpaks
flatpak info package_name          # Show flatpak information
```

## Package Troubleshooting
```bash
# Fix broken packages
apt --fix-broken install           # Fix broken dependencies
dpkg --configure -a                # Configure unconfigured packages
apt-get check                      # Check for broken dependencies

# Lock file issues
sudo rm /var/lib/dpkg/lock-frontend
sudo rm /var/lib/apt/lists/lock
sudo rm /var/cache/apt/archives/lock
```

## Package History and Logs
```bash
# Package logs
/var/log/apt/history.log           # APT history
/var/log/dpkg.log                  # DPKG log
grep " install " /var/log/dpkg.log # Show installation history
grep " remove " /var/log/dpkg.log  # Show removal history
```

---
*Author: Sujata*

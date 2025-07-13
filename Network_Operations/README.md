# Network Operations Commands

## Network Configuration
```bash
# Network interfaces
ip addr show               # Show all network interfaces
ip addr add 192.168.1.100/24 dev eth0  # Add IP address
ip addr del 192.168.1.100/24 dev eth0  # Remove IP address
ifconfig                   # Display network interfaces (deprecated)
ifconfig eth0 up           # Bring interface up
ifconfig eth0 down         # Bring interface down

# Routing
ip route show              # Show routing table
ip route add default via 192.168.1.1    # Add default route
ip route del 192.168.1.0/24             # Delete route
route -n                   # Show routing table (deprecated)
```

## Network Testing and Troubleshooting
```bash
# Connectivity testing
ping hostname              # Test connectivity
ping -c 4 hostname         # Ping 4 times only
ping6 hostname             # IPv6 ping
traceroute hostname        # Trace route to destination
tracepath hostname         # Trace path (no root required)
mtr hostname               # My traceroute (continuous)

# DNS testing
nslookup hostname          # DNS lookup
dig hostname               # DNS lookup (detailed)
dig @8.8.8.8 hostname      # Query specific DNS server
host hostname              # Simple DNS lookup
```

## Network Monitoring
```bash
# Network connections
netstat -tuln              # Show listening ports
netstat -tulpn             # Show listening ports with process info
ss -tuln                   # Socket statistics (modern netstat)
ss -tulpn                  # Socket statistics with process info
lsof -i                    # List network connections
lsof -i :80                # Connections on port 80

# Network traffic
iftop                      # Network traffic by connection
nethogs                    # Network traffic by process
nload                      # Network traffic monitor
tcpdump -i eth0            # Packet capture
wireshark                  # GUI packet analyzer
```

## Network Services
```bash
# Service testing
telnet hostname port       # Test TCP connection
nc -zv hostname port       # Test port connectivity
nc -l 1234                 # Listen on port 1234
wget http://example.com    # Download file
curl http://example.com    # Transfer data from server
curl -I http://example.com # Get headers only
```

## Firewall Management
```bash
# UFW (Uncomplicated Firewall)
ufw status                 # Check firewall status
ufw enable                 # Enable firewall
ufw disable                # Disable firewall
ufw allow 22               # Allow SSH
ufw allow 80/tcp           # Allow HTTP
ufw deny 23                # Deny telnet
ufw delete allow 80        # Remove rule

# iptables (advanced)
iptables -L                # List rules
iptables -A INPUT -p tcp --dport 22 -j ACCEPT  # Allow SSH
iptables -D INPUT -p tcp --dport 22 -j ACCEPT  # Delete rule
iptables-save              # Save current rules
```

## Network File Transfer
```bash
# File transfer
scp file.txt user@host:/path/        # Secure copy to remote
scp user@host:/path/file.txt ./      # Secure copy from remote
rsync -av source/ destination/       # Synchronize directories
rsync -av -e ssh source/ user@host:dest/  # Sync over SSH

# FTP operations
ftp hostname               # FTP client
sftp hostname              # Secure FTP
```

## Network Information
```bash
# Network statistics
cat /proc/net/dev          # Network interface statistics
ethtool eth0               # Ethernet tool info
iwconfig                   # Wireless configuration
iwlist scan                # Scan for wireless networks
```

## Network Configuration Files
```bash
# Configuration files
/etc/network/interfaces    # Network interface config (Debian/Ubuntu)
/etc/netplan/              # Netplan configuration (Ubuntu 18+)
/etc/resolv.conf           # DNS configuration
/etc/hosts                 # Static hostname resolution
/etc/hostname              # System hostname
```

## Advanced Network Tools
```bash
# Network analysis
tcptraceroute hostname port    # TCP traceroute
hping3 -S hostname -p 80      # Custom packet crafting
nmap hostname                 # Network port scanner
nmap -sS hostname             # SYN scan
arp -a                        # ARP table
ip neighbor show              # ARP table (modern)
```

---
*Author: Sujata*

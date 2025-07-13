# File Operations Commands

## Basic File and Directory Operations

### Navigation
```bash
# List directory contents
ls                    # Basic listing
ls -l                 # Long format with details
ls -la                # Include hidden files
ls -lh                # Human readable file sizes
ls -R                 # Recursive listing

# Change directory
cd /path/to/directory # Change to specific directory
cd ..                 # Go up one directory
cd ~                  # Go to home directory
cd -                  # Go to previous directory

# Print working directory
pwd                   # Show current directory path
```

### File Creation and Manipulation
```bash
# Create files
touch filename.txt           # Create empty file or update timestamp
touch file1.txt file2.txt   # Create multiple files

# Create directories
mkdir dirname               # Create single directory
mkdir -p path/to/nested/dir # Create nested directories
mkdir dir1 dir2 dir3       # Create multiple directories

# Copy files and directories
cp source.txt destination.txt        # Copy file
cp -r source_dir destination_dir     # Copy directory recursively
cp *.txt backup/                     # Copy all .txt files

# Move/rename files and directories
mv oldname.txt newname.txt          # Rename file
mv file.txt /path/to/destination/   # Move file
mv dir1 dir2                        # Rename directory

# Remove files and directories
rm filename.txt              # Remove file
rm -i filename.txt          # Remove with confirmation
rm -r directory             # Remove directory recursively
rm -rf directory            # Force remove directory
rmdir empty_directory       # Remove empty directory
```

### File Permissions and Ownership
```bash
# Change file permissions
chmod 755 filename          # Set specific permissions
chmod +x script.sh          # Add execute permission
chmod -w filename           # Remove write permission
chmod u+r,g-w,o-x filename  # Complex permission changes

# Change ownership
chown user:group filename   # Change owner and group
chown user filename         # Change owner only
chgrp group filename        # Change group only
sudo chown -R user:group directory  # Recursive ownership change
```

### File Information
```bash
# File details
stat filename               # Detailed file information
file filename               # File type information
du -h filename              # File size
du -sh directory            # Directory size summary
df -h                       # Disk space usage
```

### File Searching
```bash
# Find files and directories
find /path -name "filename"         # Find by name
find /path -type f -name "*.txt"    # Find files with extension
find /path -type d -name "dirname"  # Find directories
find /path -size +100M              # Find files larger than 100MB
find /path -mtime -7                # Find files modified in last 7 days

# Locate files (requires updatedb)
locate filename             # Quick file search
updatedb                    # Update locate database

# Which command
which command_name          # Find command location
whereis command_name        # Find command, source, manual
```

### File Comparison
```bash
# Compare files
diff file1.txt file2.txt    # Show differences
cmp file1.txt file2.txt     # Compare byte by byte
comm file1.txt file2.txt    # Compare sorted files
```

---
*Author: Sujata*

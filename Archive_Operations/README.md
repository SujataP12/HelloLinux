# Archive Operations Commands

## TAR Archives
```bash
# Create archives
tar -cvf archive.tar files/        # Create tar archive
tar -czvf archive.tar.gz files/    # Create gzipped tar archive
tar -cjvf archive.tar.bz2 files/   # Create bzip2 tar archive
tar -cJvf archive.tar.xz files/    # Create xz tar archive

# Extract archives
tar -xvf archive.tar               # Extract tar archive
tar -xzvf archive.tar.gz           # Extract gzipped tar
tar -xjvf archive.tar.bz2          # Extract bzip2 tar
tar -xJvf archive.tar.xz           # Extract xz tar
tar -xvf archive.tar -C /path/     # Extract to specific directory

# List archive contents
tar -tvf archive.tar               # List contents of tar
tar -tzvf archive.tar.gz           # List contents of gzipped tar

# Append to archives
tar -rvf archive.tar newfile       # Add file to existing tar
tar -uvf archive.tar files/        # Update files in archive
```

## ZIP Archives
```bash
# Create ZIP archives
zip archive.zip file1 file2        # Create zip with files
zip -r archive.zip directory/      # Create zip with directory
zip -r -9 archive.zip directory/   # Maximum compression
zip -r -x "*.tmp" archive.zip dir/ # Exclude pattern

# Extract ZIP archives
unzip archive.zip                  # Extract zip archive
unzip archive.zip -d /path/        # Extract to specific directory
unzip -l archive.zip               # List contents
unzip -t archive.zip               # Test archive integrity
unzip -j archive.zip               # Extract without directory structure
```

## GZIP Compression
```bash
# Compress files
gzip filename                      # Compress file (replaces original)
gzip -k filename                   # Keep original file
gzip -9 filename                   # Maximum compression
gzip -1 filename                   # Fastest compression

# Decompress files
gunzip filename.gz                 # Decompress file
gzip -d filename.gz                # Decompress file
zcat filename.gz                   # View compressed file content
```

## BZIP2 Compression
```bash
# Compress files
bzip2 filename                     # Compress file
bzip2 -k filename                  # Keep original file
bzip2 -9 filename                  # Maximum compression

# Decompress files
bunzip2 filename.bz2               # Decompress file
bzip2 -d filename.bz2              # Decompress file
bzcat filename.bz2                 # View compressed file content
```

## XZ Compression
```bash
# Compress files
xz filename                        # Compress file
xz -k filename                     # Keep original file
xz -9 filename                     # Maximum compression
xz -0 filename                     # Fastest compression

# Decompress files
unxz filename.xz                   # Decompress file
xz -d filename.xz                  # Decompress file
xzcat filename.xz                  # View compressed file content
```

## 7-Zip Archives
```bash
# Create 7z archives
7z a archive.7z files/             # Create 7z archive
7z a -mx9 archive.7z files/        # Maximum compression
7z a -t7z archive.7z files/        # Specify 7z format

# Extract 7z archives
7z x archive.7z                    # Extract with full paths
7z e archive.7z                    # Extract to current directory
7z l archive.7z                    # List contents
7z t archive.7z                    # Test archive
```

## RAR Archives
```bash
# Create RAR archives (if rar is installed)
rar a archive.rar files/           # Create rar archive
rar a -m5 archive.rar files/       # Maximum compression

# Extract RAR archives
unrar x archive.rar                # Extract with full paths
unrar e archive.rar                # Extract to current directory
unrar l archive.rar                # List contents
unrar t archive.rar                # Test archive
```

## Archive Information and Testing
```bash
# Archive information
file archive.*                     # Identify archive type
du -h archive.*                    # Show archive sizes
ls -lh archive.*                   # List archive details

# Test archive integrity
tar -tvf archive.tar > /dev/null   # Test tar archive
unzip -t archive.zip               # Test zip archive
gzip -t archive.gz                 # Test gzip file
bzip2 -t archive.bz2               # Test bzip2 file
xz -t archive.xz                   # Test xz file
```

## Backup Operations
```bash
# System backup examples
tar -czvf backup-$(date +%Y%m%d).tar.gz /home/user/  # Date-stamped backup
tar --exclude='*.tmp' -czvf backup.tar.gz /home/     # Exclude temporary files
rsync -av --delete source/ backup/                   # Incremental backup

# Restore operations
tar -xzvf backup.tar.gz -C /restore/path/            # Restore to specific location
rsync -av backup/ /restore/path/                     # Restore with rsync
```

## Advanced Archive Operations
```bash
# Split large archives
split -b 100M archive.tar.gz archive.tar.gz.part.   # Split into 100MB parts
cat archive.tar.gz.part.* > archive.tar.gz          # Rejoin split archive

# Archive with encryption
gpg -c archive.tar.gz              # Encrypt archive with password
gpg archive.tar.gz.gpg             # Decrypt archive

# Network archives
tar -czf - /path/to/backup | ssh user@host 'cat > backup.tar.gz'  # Backup over SSH
ssh user@host 'tar -czf - /remote/path' | tar -xzf -              # Extract from remote
```

## Archive Comparison
```bash
# Compare archives
diff <(tar -tf archive1.tar | sort) <(tar -tf archive2.tar | sort)  # Compare tar contents
zdiff file1.gz file2.gz            # Compare compressed files
```

## Compression Ratios
```bash
# Compare compression methods
ls -l original_file                # Original size
gzip -k original_file && ls -l original_file.gz     # Gzip size
bzip2 -k original_file && ls -l original_file.bz2   # Bzip2 size
xz -k original_file && ls -l original_file.xz       # XZ size
```

---
*Author: Sujata*

# Text Processing Commands

## File Viewing and Reading
```bash
# Display file contents
cat filename                       # Display entire file
cat -n filename                    # Display with line numbers
cat -b filename                    # Number non-blank lines
tac filename                       # Display in reverse order

# Paging through files
less filename                      # View file with paging
more filename                      # Simple pager
head filename                      # First 10 lines
head -n 20 filename                # First 20 lines
tail filename                      # Last 10 lines
tail -n 20 filename                # Last 20 lines
tail -f filename                   # Follow file changes
```

## Text Searching
```bash
# Search within files
grep "pattern" filename            # Search for pattern
grep -i "pattern" filename         # Case-insensitive search
grep -r "pattern" directory        # Recursive search
grep -n "pattern" filename         # Show line numbers
grep -v "pattern" filename         # Invert match (exclude)
grep -c "pattern" filename         # Count matches
grep -l "pattern" *.txt            # List files with matches
grep -A 3 -B 3 "pattern" filename  # Show 3 lines before/after

# Advanced grep
egrep "pattern1|pattern2" filename # Extended regex
fgrep "literal string" filename    # Fixed string search
zgrep "pattern" file.gz            # Search in compressed files
```

## Text Manipulation
```bash
# Sort and unique
sort filename                      # Sort lines alphabetically
sort -n filename                   # Numeric sort
sort -r filename                   # Reverse sort
sort -k 2 filename                 # Sort by column 2
sort -u filename                   # Sort and remove duplicates
uniq filename                      # Remove adjacent duplicates
uniq -c filename                   # Count occurrences
uniq -d filename                   # Show only duplicates

# Cut and paste
cut -d',' -f1,3 filename          # Extract columns 1 and 3 (CSV)
cut -c1-10 filename               # Extract characters 1-10
paste file1 file2                 # Merge files side by side
paste -d',' file1 file2           # Merge with comma delimiter
```

## Text Transformation
```bash
# Case conversion
tr '[:lower:]' '[:upper:]' < file  # Convert to uppercase
tr '[:upper:]' '[:lower:]' < file  # Convert to lowercase
tr -d ' ' < file                   # Delete spaces
tr ' ' '_' < file                  # Replace spaces with underscores
tr -s ' ' < file                   # Squeeze multiple spaces

# Text replacement
sed 's/old/new/' filename          # Replace first occurrence per line
sed 's/old/new/g' filename         # Replace all occurrences
sed 's/old/new/gi' filename        # Case-insensitive replacement
sed -i 's/old/new/g' filename      # In-place replacement
sed '1,5s/old/new/g' filename      # Replace in lines 1-5
sed '/pattern/d' filename          # Delete lines matching pattern
```

## Field and Column Processing
```bash
# AWK text processing
awk '{print $1}' filename          # Print first column
awk '{print $1, $3}' filename      # Print columns 1 and 3
awk -F',' '{print $2}' filename    # Use comma as delimiter
awk '{sum += $1} END {print sum}' filename  # Sum first column
awk 'length > 80' filename         # Lines longer than 80 chars
awk '/pattern/ {print $0}' filename # Print lines matching pattern
awk 'NR==5' filename               # Print line 5
awk 'NF > 3' filename              # Lines with more than 3 fields
```

## Text Statistics
```bash
# Word and character counts
wc filename                        # Lines, words, characters
wc -l filename                     # Count lines only
wc -w filename                     # Count words only
wc -c filename                     # Count characters only
wc -m filename                     # Count characters (multibyte)
```

## Text Comparison
```bash
# Compare files
diff file1 file2                   # Show differences
diff -u file1 file2                # Unified diff format
diff -y file1 file2                # Side-by-side comparison
cmp file1 file2                    # Compare byte by byte
comm file1 file2                   # Compare sorted files
```

## Advanced Text Processing
```bash
# Stream editing
sed -n '1,10p' filename            # Print lines 1-10
sed '5d' filename                  # Delete line 5
sed '/^$/d' filename               # Delete empty lines
sed 'G' filename                   # Double space file
sed '/pattern/i\text' filename     # Insert text before pattern

# Multiple file processing
cat file1 file2 > combined         # Concatenate files
join file1 file2                   # Join files on common field
split -l 1000 largefile            # Split file into 1000-line chunks
csplit filename /pattern/          # Split file at pattern
```

## Text Formatting
```bash
# Format text
fmt filename                       # Format paragraphs
fmt -w 60 filename                 # Format to 60 characters width
fold -w 80 filename                # Wrap lines at 80 characters
expand filename                    # Convert tabs to spaces
unexpand filename                  # Convert spaces to tabs
column -t filename                 # Columnate text
```

## Regular Expressions
```bash
# Common regex patterns
grep '^pattern' filename           # Lines starting with pattern
grep 'pattern$' filename           # Lines ending with pattern
grep '^$' filename                 # Empty lines
grep '[0-9]' filename              # Lines containing digits
grep '[A-Z]' filename              # Lines containing uppercase
grep '.' filename                  # Lines with any character
grep 'a\{3\}' filename             # Lines with 'aaa'
```

## Text Encoding
```bash
# Character encoding
iconv -f utf8 -t ascii filename    # Convert encoding
file filename                      # Detect file encoding
hexdump -C filename                # Hex dump of file
od -c filename                     # Octal dump with characters
```

---
*Author: Sujata*

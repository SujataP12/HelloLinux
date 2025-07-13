# Development Tools Commands

## Version Control (Git)
```bash
# Repository management
git init                          # Initialize repository
git clone url                     # Clone repository
git status                        # Show working tree status
git add file                      # Stage file
git add .                         # Stage all changes
git commit -m "message"           # Commit changes
git push origin main              # Push to remote
git pull origin main              # Pull from remote
git fetch                         # Fetch from remote

# Branch management
git branch                        # List branches
git branch branch_name            # Create branch
git checkout branch_name          # Switch branch
git checkout -b branch_name       # Create and switch branch
git merge branch_name             # Merge branch
git branch -d branch_name         # Delete branch

# History and logs
git log                           # Show commit history
git log --oneline                 # Compact log
git log --graph                   # Graph view
git diff                          # Show changes
git diff --staged                 # Show staged changes
git show commit_hash              # Show specific commit
```

## Compilation and Build Tools
```bash
# GCC Compiler
gcc -o program source.c           # Compile C program
gcc -Wall -g -o program source.c  # Compile with warnings and debug
g++ -o program source.cpp         # Compile C++ program
gcc -c source.c                   # Compile to object file
gcc -shared -o lib.so source.c    # Create shared library

# Make build system
make                              # Build using Makefile
make clean                        # Clean build files
make install                      # Install built program
make -j4                          # Parallel build with 4 jobs
make -f custom.mk                 # Use custom Makefile
```

## Debugging Tools
```bash
# GDB Debugger
gdb program                       # Start debugger
gdb -args program arg1 arg2       # Debug with arguments
gdb --batch --ex run --ex bt program  # Batch mode debugging

# GDB commands (inside gdb)
(gdb) run                         # Run program
(gdb) break main                  # Set breakpoint
(gdb) continue                    # Continue execution
(gdb) step                        # Step into
(gdb) next                        # Step over
(gdb) print variable              # Print variable value
(gdb) backtrace                   # Show call stack
(gdb) quit                        # Exit debugger

# Other debugging tools
strace program                    # Trace system calls
ltrace program                    # Trace library calls
valgrind program                  # Memory debugging
valgrind --leak-check=full program # Memory leak detection
```

## Text Editors and IDEs
```bash
# Vim editor
vim filename                      # Open file in vim
vim +10 filename                  # Open at line 10
vim -R filename                   # Open read-only
vimdiff file1 file2               # Compare files

# Nano editor
nano filename                     # Open file in nano
nano +10 filename                 # Open at line 10
nano -w filename                  # Disable word wrap

# Emacs editor
emacs filename                    # Open file in emacs
emacs -nw filename                # Terminal mode
```

## Programming Language Tools
```bash
# Python
python3 script.py                 # Run Python script
python3 -m pip install package   # Install Python package
python3 -m venv venv              # Create virtual environment
source venv/bin/activate          # Activate virtual environment
python3 -c "print('Hello')"       # Execute Python code
python3 -m http.server 8000       # Simple HTTP server

# Node.js and npm
node script.js                    # Run Node.js script
npm init                          # Initialize npm project
npm install package               # Install npm package
npm install -g package            # Install globally
npm start                         # Start application
npm test                          # Run tests

# Java
javac Program.java                # Compile Java program
java Program                      # Run Java program
jar -cf archive.jar files         # Create JAR file
java -jar program.jar             # Run JAR file
```

## Database Tools
```bash
# MySQL/MariaDB
mysql -u user -p                  # Connect to MySQL
mysqldump -u user -p database > backup.sql  # Backup database
mysql -u user -p database < backup.sql      # Restore database

# PostgreSQL
psql -U user -d database          # Connect to PostgreSQL
pg_dump database > backup.sql     # Backup database
psql -U user -d database < backup.sql       # Restore database

# SQLite
sqlite3 database.db               # Open SQLite database
sqlite3 database.db ".dump" > backup.sql    # Backup SQLite
```

## Container Tools
```bash
# Docker
docker build -t image_name .      # Build Docker image
docker run -it image_name         # Run container interactively
docker run -d -p 8080:80 image    # Run container in background
docker ps                         # List running containers
docker ps -a                      # List all containers
docker images                     # List images
docker stop container_id          # Stop container
docker rm container_id            # Remove container
docker rmi image_id               # Remove image

# Docker Compose
docker-compose up                 # Start services
docker-compose up -d              # Start in background
docker-compose down               # Stop services
docker-compose logs               # View logs
```

## Package Managers and Dependencies
```bash
# APT (system packages)
apt search package                # Search packages
apt show package                  # Show package info
apt install package               # Install package
apt remove package                # Remove package

# Snap packages
snap find package                 # Search snap packages
snap install package              # Install snap package
snap list                         # List installed snaps

# Flatpak packages
flatpak search package            # Search flatpak packages
flatpak install package           # Install flatpak package
flatpak list                      # List installed flatpaks
```

## Performance and Profiling Tools
```bash
# Performance monitoring
time command                      # Time command execution
/usr/bin/time -v command          # Detailed timing info
perf record command               # Record performance data
perf report                       # Analyze performance data
htop                              # Interactive process viewer
iotop                             # I/O monitoring
```

## Code Analysis Tools
```bash
# Static analysis
cppcheck source.cpp               # C++ static analysis
pylint script.py                  # Python code analysis
shellcheck script.sh              # Shell script analysis
clang-format source.cpp           # Format C++ code
black script.py                   # Format Python code
```

## Documentation Tools
```bash
# Manual pages
man command                       # Show manual page
man -k keyword                    # Search manual pages
info command                      # Show info page
command --help                    # Show help
which command                     # Find command location
type command                      # Show command type
```

## Archive and Distribution
```bash
# Creating packages
tar -czf project.tar.gz project/  # Create source archive
zip -r project.zip project/       # Create zip archive
dpkg-deb --build package/         # Build Debian package
rpmbuild -ba package.spec         # Build RPM package
```

---
*Author: Sujata*

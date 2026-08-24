# Linux Fundamentals — Command Cheat Sheet

## File Traversal

```bash
cd <directory>          # Change directory
cd ..                   # Go back one directory
cd /etc                 # System-wide configuration/data
pwd                     # Print working directory

find ~ -name <filename> # Search from home directory by filename

ls                      # List files
ls -l                   # Long/detailed listing
ls -al                  # List all files in long format
ls -h                   # Human-readable file sizes

whoami                  # Display current username

uname                   # Display kernel name
uname -a                # Display detailed system information

touch <file>            # Create a file
mkdir <directory>       # Create a directory
rm <file>               # Remove a file/directory
mv <file> <directory>   # Move a file/directory
file <file>             # Determine file type
```

### Important Directories

```text
/etc     System-wide configuration/data
/var     Variable data, such as logs (/var/log)
/root    Root user's home directory
/tmp     Temporary files
```

## Shells

```text
zsh
```

## Users, Logs & System Information

```bash
ssh <username>@<address/domain>    # Connect to a remote host

su - <username>                    # Switch user
su -l <username>                   # Switch user with login environment

history                            # View command history
date                               # Display current date/time

echo "This outputs this text"      # Output text

grep "Find x" <filename>           # Search for text inside a file
```

## Combining Commands

```bash
mkdir project &                    # Run command in the background

mkdir project && cd project && touch main.cpp
# Run next command only if the previous command succeeds

echo "example" > file.txt          # Write output; overwrites existing content

echo "example" >> file.txt        # Append output without overwriting
```

## File Transfer & Web Servers

```bash
wget <URL>                         # Download a file

scp <source> <destination>         # Securely copy files

scp user@domain:a b                # Copy 'a' from remote host to 'b'

scp ubuntu@192.168.1.32:/home/ubuntu/documents.txt notes.txt
# Copy a remote file to the local machine

python3 -m http.server              # Start a Python HTTP server

wget http://10.49.183.54:8000/.flag.txt
# Download a file from a server running on port 8000
```

## Editing Files

```bash
nano <filename>                    # Edit a file
```

## Processes

```bash
ps                                 # View currently running processes
ps aux                             # View processes from all users
top                                # Real-time process statistics

kill <PID>                         # Terminate a process
```

### Signals

```text
SIGTERM    Terminate process and allow cleanup
SIGKILL    Immediately terminate process
SIGSTOP    Stop/suspend a process
```

```bash
Ctrl + Z                            # Suspend/background a process
fg                                  # Bring a background process to the terminal
```

## Services — systemctl

```bash
systemctl [option] [service]

systemctl start apache2            # Start service
systemctl stop apache2             # Stop service
systemctl enable apache2           # Enable service at boot
systemctl disable apache2          # Disable service at boot
systemctl status apache2            # View service status
```

## Scheduled Tasks

```bash
crontab -l                         # List scheduled cron jobs

add-apt-repository                 # Add an APT repository
```

## Apache Logs

```text
/var/log/apache2/
```

Apache access and error logs are stored here.

## GPG

```bash
gpg --full-gen-key                 # Generate a GPG key
gpg --import <keyname.key>         # Import a key
gpg --decrypt <confidential_message.gpg>  # Decrypt a file
```

GPG can be used for **signing, encryption, and decryption**.

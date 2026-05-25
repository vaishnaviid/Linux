# Linux commands for DevOps
## Connecting Windows to Linux
                                                                                                                                                                           
To connect from Windows → Linux server, use tools:
- Git Bash
- PuTTY                                                    
- WinSCP                                                                            
- MobaXterm
                                                                                                                                                                                                                                                                
## 🔑 SSH & Keys                                                                                                                                            
                                                                          
Communication between client and server happens via SSH.

Uses public & private key pairs (ssh-keygen).

Public key → stored in server.

Private key → stored locally.
## 🐧 Linux Operating System
- Free and open-source.
- Community-based.
- High security.
- Multi-user system.
- CLI-based OS.
- Widely used in businesses & servers.

## 📦 Popular Linux Distributions
- Amazon Linux
- Red Hat Linux
- CentOS
- SUSE Linux
- Ubuntu
- Debian

## 📂 Linux File System

Everything is represented as a file.

### File types:

- `-` → Ordinary/Normal File

- d → Directory File (Folder)

- l → Link File (Shortcut)

- . → Hidden File

# 📋 Basic Linux Commands
## Navigation
```
ls              # List files
ls -l           # Long listing
ls -la          # Show hidden files
ls -ltr         # Show oldest files first
pwd             # Print working directory
cd dirname      # Change directory
cd ..           # Go back
cd ~            # Home directory
clear           # Clear terminal
```

## File & Directory Management
```
mkdir dirname   # Create directory
rmdir dirname   # Remove empty directory
rm filename     # Remove file
rm -rf dirname  # Remove non-empty directory
mv old new      # Rename file
mv file dir/    # Move file
cp src dest     # Copy file
touch file      # Create empty file
cat > file      # Create file + write content
cat >> file     # Append content
cat file        # Display content
cat f1 f2 > f3  # Merge files
cat -n file     # Show line numbers
tac file        # Print file bottom → top
rev file        # Reverse lines
```
## Viewing
```
head file       # First 10 lines
head -n 5 file  # First 5 lines
tail file       # Last 10 lines
tail -n 5 file  # Last 5 lines
tail -f file    # Watch live file changes
less file       # Page by page view
sort file       # Sort file lines
```
## Search
```
grep 'word' file        # Search case-sensitive
grep -i 'word' file     # Case-insensitive
grep -n 'word' file     # Show line number
grep -v 'word' file     # Invert match
```

## ⚙️ Process Management
```
top         # Running processes
ps          # Process IDs
fuser       # Show process using a file
kill -9 PID # Kill process
free -h     # Memory usage
vmstat      # RAM usage stats
nohup cmd   # Run command in background with logs
```
## 📝 Text Processing Tools (sed & awk)
```
sed (Stream Editor)
sed 's/old/new/' file      # Replace first occurrence
sed 's/old/new/g' file     # Replace all
sed -i 's/old/new/g' file  # Replace permanently
sed '4d' file              # Delete line 4
sed '$d' file              # Delete last line
sed -n '3,6p' file         # Print lines 3-6
sed '/word/p' file         # Print lines with word
sed '/word/d' file         # Delete lines with word

awk
awk '/word/ {print}' file     # Print lines with word
awk '{print $3,$7}' file      # Print columns 3 & 7
awk '{print NR, $0}' file     # Print with line numbers
awk '{print NR "-" $1}' file  # Line numbers + first column
```

## 👥 User & Group Management
### Users
```
sudo useradd username
sudo passwd username
sudo su username      # Switch user
sudo userdel username
sudo userdel -r username   # Delete with home dir
```
### Groups
```
sudo groupadd grpname
sudo gpasswd -a user grp   # Add user to group
sudo usermod -aG grp user  # Add user to group
sudo gpasswd -M u1,u2 grp  # Add multiple users
sudo gpasswd -d user grp   # Remove from group
sudo groupdel grpname
```

## 📂 File Permissions

Permissions: read (r), write (w), execute (x)

Entities: user (u), group (g), others (o)

Change permissions
chmod u+rwx file
chmod g-r file
chmod o+x file

Numeric format
7 = rwx
6 = rw-
5 = r-x
4 = r--
3 - -wx
2 - -w-
1 - --x
0 = ---

Default: (when umask is 0002)
- Files → 644
- Directories → 755

### 👤 Ownership
```
sudo chown user file
sudo chown :group file
sudo chown user:group file
```

### 📦 Archiving & Compression
```
zip file.zip file1 file2
zip -r archive.zip dir/
unzip file.zip
```

## 🌐 Networking Commands
```
ping host
wget url
curl url
ifconfig
traceroute host
tracepath host
nslookup domain
dig domain
mtr host
whois domain
```

## 🔁 Local ↔ Remote File Management
```
#Copy file from local → remote
scp file.txt user@remote:/path/

# Copy file from remote → local
scp user@remote:/path/file.txt ./

# rsync (sync files & dirs)
rsync -av file user@remote:/path/
```
## 💽 Linux Volume Management
LVM → Logical Volume Manager
```
lsblk   # List disks
df -h   # Disk usage
du .    # Disk usage by dir
```



##  📦 Package Managers
- Amazon Linux / RHEL / CentOS → yum
- Ubuntu / Debian → apt

Examples:
```
sudo yum update -y
sudo yum install httpd -y
sudo apt update && sudo apt install nginx -y
```

## 🌍 Install Web Servers
```
# Apache (httpd)
sudo yum install httpd -y
sudo systemctl start httpd
sudo systemctl stop httpd
sudo systemctl restart httpd
sudo systemctl enable httpd
sudo systemctl disable httpd
cd /var/www/html              # default html path  
```

## 🏷️ Changing Hostname
```
sudo hostname newname
```


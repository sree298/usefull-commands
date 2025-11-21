# 📘 LINUX COMMANDS CHEAT SHEET

## 📂 Directory Navigation
| Command | Description | Syntax | Example |
|--------|------------|--------|---------|
| pwd | Display present working directory | `pwd` | `pwd` |
| cd | Move to directory | `cd <path>` | `cd /var/log` |
| cd /etc | Change to /etc directory | `cd /etc` | `cd /etc` |

---

## 📁 File & Directory Commands
| Command | Description | Syntax | Example |
|--------|------------|--------|---------|
| ls | List files & directories | `ls` | `ls` |
| ls -a | List including hidden files | `ls -a` | `ls -a` |
| ls -lrth | Long listing readable format | `ls -lrth` | `ls -lrth` |
| touch | Create file | `touch <file>` | `touch test.txt` |
| mkdir | Create directory | `mkdir <dir>` | `mkdir /home/ubuntu/web-colour` |
| mkdir -p | Create parent directories if not existing | `mkdir -p <dir-path>` | `mkdir -p /home/ubuntu/project/src` 
| rm | Remove file | `rm <file>` | `rm test.txt` |
| rm -rf | Force delete | `rm -rf <dir/file>` | `rm -rf web-colour` |
| cp | Copy file | `cp file1 file2` | `cp test4.txt test44.txt` |
| mv | Move/Rename file | `mv <src> <dest>` | `mv future tech` |
| ln -s | Create symbolic link | `ln -s /path/file link` | `ln -s /usr/bin/python my-python` |
| cat | View file content | `cat <file>` | `cat future-tech` |
| less | Browse file | `less <file>` | `less future-tech` |
| head | First 10 lines | `head <file>` | `head future-tech` |
| tail | Last 10 lines | `tail <file>` | `tail future-tech` |

---

## 🖥 System Information
| Command | Description |
|--------|-------------|
| `cat /etc/os-release` | OS version |
| `uptime` | System running time |
| `hostname` | Hostname |
| `hostname -I` | IP addresses |
| `last reboot` | Reboot history |
| `date` | Current time |
| `w` | Who is online |
| `whoami` | Logged user |
| `uname -a` | System info |
| `uname -r` | Kernel version |

---

## 🧠 Hardware Information
| Command | Description |
|--------|-------------|
| `cat /proc/cpuinfo` | CPU details |
| `free -h` | Memory usage |
| `df -h` | Disk usage |

---

## 📊 Process & Performance Monitoring
| Command | Description |
|--------|-------------|
| `top` | Running processes |
| `htop` | Interactive process viewer |
| `lsof` | Open files |
| `lsof -u <user>` | Files opened by user |

---

## 👤 User & Group Management
| Command | Description | Example |
|--------|------------|---------|
| `id` | User info | `id` |
| `last` | Login history | `last` |
| `groupadd` | Create group | `groupadd dev` |
| `useradd` | Create user | `useradd -g dev -d /home/john john` |
| `usermod -aG` | Add to group | `usermod -aG sales john` |
| `userdel` | Delete user | `userdel john` |

---

## 🗜 Archiving (TAR)
| Command | Description |
|--------|-------------|
| `tar cf file.tar dir` | Create tar |
| `tar xf file.tar` | Extract tar |
| `tar czf file.tgz dir` | Create gzip tar |
| `tar xzf file.tar.gz` | Extract gzip tar |

---

## 🔧 Process Management
| Command | Description | Syntax | Example |
|--------|------------|--------|---------|
| ps -ef | Display process information | `ps -ef \| grep <process-name>` | `ps -ef \| grep redis` |
| top | Display and manage top processes | `top` | `top` |
| htop | Interactive process viewer | `htop` | `htop` |
| kill | Kill process by PID | `kill <pid>` | `kill 1234` |
| kill -9 | Forcefully kill process | `kill -9 <pid>` | `kill -9 1234` |
| program & | Start program in background | `program &` | `program &` |

---

## 🔐 File Permissions

4 = Read, 2 = Write, 1 = Execute
chmod 777 filename
chmod 777 sai

## 🌐 Networking

| Command | Description |
|--------|-------------|
| `ifconfig -a` | Show all network interface details |
| `ping <host>` | Test connectivity (ICMP) |
| `whois <domain>` | WHOIS lookup for domain information |
| `host <domain>` | DNS lookup |
| `netstat -ntplu` | List listening ports with process & protocol info |
| `wget <url>` | Download files from the internet |
| `hostname -I` | Display local IP addresses |

## 🍱 YUM / RPM Package Management

| Command             | Description     |
| ------------------- | --------------- |
| `yum search <pkg>`  | Search package  |
| `yum install <pkg>` | Install package |
| `yum remove <pkg>`  | Remove package  |
| `rpm -i file.rpm`   | Install rpm     |

## 🔍 File & Text Search Commands

| Command                      | Description        |
| ---------------------------- | ------------------ |
| `grep <key> <file>`          | Search keyword in file |
| `grep -r <key> <dir>`        | Recursive search in directory |
| `grep -lr <key> <dir>`       | List only matching file names |
| `locate <name>`              | Find file by name (uses DB) |
| `find /home -name 'prefix*'` | Find file by name pattern   |
| `find /home -size +100M`     | Find files larger than 100MB |

## 🔐 SSH Commands

| Command                   | Description   |
| ------------------------- | ------------- |
| `ssh host`                | Connect to remote host |
| `ssh user@host`           | Login as specific user |
| `ssh -p <port> user@host` | Connect using custom port |

## 🚚 File Transfer (SCP / Rsync)

| Command                             | Description        |
| ----------------------------------- | ------------------ |
| `scp file.txt server:/tmp`          | Copy file to remote server |
| `scp -r server:/var/www /tmp`       | Copy directory from remote to local |
| `rsync -avz /home server:/backups/` | Sync directory efficiently for backup |

## ✏️ Text Processing Commands

| Command               | Description        |
| --------------------- | ------------------ |
| `grep -i 'Pass' file` | Case-insensitive search in file |
| `awk '{print $9}'`    | Extract 9th column from input   |
| `sed`                 | Stream editor for search & replace |

## 🧰 Other Useful Commands

| Command                         | Description            |
| ------------------------------- | ---------------------- |
| `chown ubuntu:ubuntu /tmp/test` | Change file owner & group |
| `nslookup google.com`           | DNS lookup / test      |
| `telnet <ip> <port>`            | Check port connectivity |
| `curl -av <ip:port>`            | Test connectivity / verbose |
| `history`                       | Show last executed commands |

## 📋 Troubleshooting Checklist

1. **Check server status**
   - `systemctl status <service>`
   - `uptime`
   - `top` / `htop`
   - `free -m`
   - `df -h`

2. **Check connectivity between servers**
   - `ping <server>`
   - `telnet <ip> <port>`
   - `nc -zv <ip> <port>`
   - `ssh user@host`

3. **Check application status**
   - `systemctl status <app>`
   - `ps -ef | grep <app>`
   - `curl -I http://<ip>:<port>`

4. **Verify port listening**
   - `netstat -ntplu`
   - `ss -tulnp`
   - `lsof -i :<port>`

5. **Test from same node**
   - `curl -I http://localhost:<port>`
   - `telnet localhost <port>`
   - `nc -zv localhost <port>`

6. **Review logs**
   - `tail -f /var/log/messages`
   - `tail -f /var/log/syslog`
   - `tail -f /var/log/<app>.log`




















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
```bash
4 = Read, 2 = Write, 1 = Execute
chmod 777 filename
chmod 777 sai

## 🌐 Networking Commands








# 🐧 My Linux Learning Journey

## 📌 Getting Started
As someone new to Linux, I embarked on a journey to understand the fundamentals, navigate the command line, and configure my system effectively. This document captures what I learnt along the way and the key areas I focused on. 🚀

---

## 🔥 Essential Commands I Practised
| Command          | What I Learnt                                          |
|-----------------|------------------------------------------------------|
| `ls`           | Lists files and directories to explore the system.  |
| `pwd`          | Helps to know my current working directory.        |
| `cd <dir>`     | Used to move between directories.                   |
| `mkdir <dir>`  | Creates new directories for better organisation.   |
| `rmdir <dir>`  | Deletes empty directories when no longer needed.   |
| `rm -r <dir>`  | Removes a directory along with its contents.       |
| `cp <file> <destination>`  | Copies files to another location.       |
| `mv <file> <destination>`  | Moves/renames files or directories.     |
| `touch <file>` | Creates empty files for quick editing.             |
| `echo <text>`  | Outputs text or writes it to a file.               |
| `cat <file>`   | Displays file contents quickly.                    |
| `grep <pattern> <file>` | Searches for specific text in files.      |
| `head <file>`  | Shows the first few lines of a file.               |
| `tail <file>`  | Shows the last few lines of a file.                |

---

## ⚙️ Understanding the Linux File System
As I explored Linux, I realised the file system is structured differently from Windows. Here are some key directories I became familiar with:

| Directory | What I Learnt |
|-----------|--------------|
| `/`       | The root directory where everything starts. |
| `/home/`  | Where user files and settings are stored. |
| `/bin/`   | Contains essential system binaries (commands). |
| `/etc/`   | Stores configuration files for the system. |
| `/var/`   | Contains logs and dynamic system data. |
| `/tmp/`   | Used for temporary files that get deleted automatically. |
| `/usr/`   | Holds applications and utilities for everyday use. |

---

## 🛠️ Learning Vim (Text Editor)
Initially, Vim felt confusing, but after practising, I started to understand its modes and shortcuts.

**Modes in Vim:**
- **Normal Mode** (default) ➝ Used for navigation and commands.
- **Insert Mode** ➝ Activated with `i` to start typing.
- **Visual Mode** ➝ Enabled with `v` to select text.

**Commands I Found Useful:**
| Command  | Action |
|----------|--------|
| `dd`     | Deletes the current line. |
| `yy`     | Copies the current line. |
| `p`      | Pastes copied text. |
| `u`      | Undoes the last action. |
| `Ctrl + r` | Redoes the last undone change. |
| `:wq`    | Saves and exits. |
| `:q!`    | Exits without saving. |

---

## 🔑 Understanding User Management & Permissions
One key concept I had to grasp was user roles and permissions.

**User Management Commands I Practised:**
| Command | Purpose |
|---------|---------|
| `sudo useradd <username>` | Adds a new user. |
| `sudo passwd <username>` | Sets a password for a user. |
| `su - <username>` | Switches to another user. |
| `sudo deluser <username>` | Removes a user. |

**File Permissions:**
| Permission | Meaning |
|------------|---------|
| `r`        | Read access. |
| `w`        | Write access. |
| `x`        | Execute access (for scripts/programs). |

To modify permissions, I used:
- `chmod 755 file`: Sets **rwx** for the owner and **r-x** for others.
- `chown user:group file`: Changes ownership of a file.

---

## 🖥️ Exploring Different Shells
I learnt that different shells provide different functionalities. The most common ones include:
- **Bash** (default on most systems)
- **Zsh** (customisable, especially with `Oh My Zsh`)

To check my shell, I used:
```bash
echo $SHELL
```

To switch to Zsh:
```bash
chsh -s $(which zsh)
```

---

## 🏗️ Understanding Environment Variables & Aliases
### 📌 Environment Variables I Found Useful
| Variable  | Purpose |
|-----------|---------|
| `PATH`    | Specifies directories for executable files. |
| `HOME`    | Stores the path of the home directory. |
| `USER`    | Shows the currently logged-in user. |
| `SHELL`   | Displays the active shell. |

### 🎯 Creating Aliases to Simplify Commands
To speed up my workflow, I created aliases:
```bash
alias ll='ls -la'
alias rmrf='rm -rf'
```
To remove an alias:
```bash
unalias ll
```

---

## ⚡ Linux Command Shortcuts I Found Useful
| Shortcut     | Action |
|-------------|--------|
| `Ctrl + C`  | Stops a running command. |
| `Ctrl + Z`  | Suspends a running process. |
| `Ctrl + R`  | Searches command history. |
| `!!`        | Repeats the last command. |
| `!<num>`    | Runs a command from history by number. |
| `history`   | Displays command history. |

---

## 🌍 Experimenting with Remote Access & Virtual Machines
- Used `ssh user@server-ip` to connect to remote servers.
- Transferred files using:
```bash
scp file user@server-ip:/path/
```
- Set up a virtual Linux environment using:
  - VirtualBox (for Windows users)
  - UTM (for Mac users)

---

## 🎮 Practising with Linux Challenges
To improve my skills, I played **OverTheWire: Bandit**, which helped me understand Linux security and commands: [https://overthewire.org/wargames/bandit/](https://overthewire.org/wargames/bandit/) 🕹️

---

## 💡 Reflecting on My Linux Learning Journey
Linux was challenging at first, but every mistake I made was an opportunity to learn. My key takeaway:
```
The best way to learn Linux is to break things and fix them! 🛠️
```
Excited to keep exploring! 🐧💻


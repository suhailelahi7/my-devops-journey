# 🏴‍☠️ My Bandit Linux Challenge Journey (Levels 0-20)

## Introduction
When I first started **OverTheWire's Bandit** war game, I was excited but also quite nervous. I had used Linux before, but this was my first real challenge in navigating a system with just the command line. Here’s a log of my personal journey through **Bandit**, including how I tackled each level, the **commands I used**, and the **challenges I faced** along the way. Hopefully, my experiences will help fellow beginners avoid common pitfalls!

---

## Level 0: My First SSH Connection
### Objective: SSH into the Bandit server.
📌 **Command:** 
```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```
✅ **Password = bandit0**

📝 **Challenges I Faced:** 
- I initially forgot to specify the port with `-p 2220`, which resulted in a connection error.
- Had a moment of panic when I saw `Permission denied`—but I was just mistyping the username!
- Finally got in and was thrilled to see the prompt change!

---

## Level 0 → 1: My First Password Hunt
📌 **Steps:**
1. List the files: 
   ```bash
   ls
   ```
2. Read the `readme` file:
   ```bash
   cat readme
   ```
✅ **Password = ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If**

📝 **Challenges I Faced:**
- At first, I typed `cat ReadMe` instead of `readme` (Linux is case-sensitive!).
- Realised I should always use `ls` first to confirm the exact filename.

---

## Level 1 → 2: Tricky Filename with `-`
📌 **Steps:**
1. List files: 
   ```bash
   ls
   ```
2. Read the tricky file:
   ```bash
   cat ./-
   ```
✅ **Password = 263JGJPfgU6LtdEvgfWU1XP5yac29mFx**

📝 **Challenges I Faced:**
- Entered `cat -` at first, which didn’t work—it was waiting for input instead!
- Learned that using `./` before a filename helps avoid issues with special characters.

---

## Level 2 → 3: Handling Spaces in Filenames
📌 **Steps:**
1. List files:
   ```bash
   ls
   ```
2. Use escape sequences:
   ```bash
   cat spaces\ in\ this\ filename
   ```
🚀 **Alternative:** Press `Tab` for auto-completion.

✅ **Password = MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx**

📝 **Challenges I Faced:**
- I forgot to escape spaces (`\`) and got an error at first.
- Also discovered that enclosing filenames in quotes works too: `cat "spaces in this filename"`.

---

## Level 3 → 4: Hidden Files Surprise
📌 **Steps:**
1. Navigate into the `inhere` directory:
   ```bash
   cd inhere
   ```
2. List hidden files:
   ```bash
   ls -a
   ```
3. Read the hidden file:
   ```bash
   cat .hidden
   ```
✅ **Password = 2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ**

📝 **Challenges I Faced:**
- At first, I only used `ls`, not `ls -a`, and thought the folder was empty!
- Now I always use `ls -a` to check for hidden files.

---

## Level 4 → 5: Finding the Right File
📌 **Steps:**
1. Enter `inhere`:
   ```bash
   cd inhere
   ```
2. Identify the correct file:
   ```bash
   file ./-file*
   ```
3. Read the ASCII text file:
   ```bash
   cat ./-file07
   ```
✅ **Password = 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw**

📝 **Challenges I Faced:**
- I initially tried `cat` on multiple files before using `file` to check file types.
- `file *` was a life-saver in identifying human-readable text files.

---

## Level 5 → 6: Searching for a Specific File
📌 **Steps:**
1. Find the correct file:
   ```bash
   find . -type f -size 1033c ! -executable
   ```
2. Read the file:
   ```bash
   cat ./maybehere07
   ```
✅ **Password = HWasnPhtq9AVKe0dmk45nxy20cvUa6EG**

📝 **Challenges I Faced:**
- Initially ran `ls`, but it didn’t help—I had to use `find`.
- Refined my search multiple times before getting the right result.

---

## Level 6 → 7: Searching the Entire System
📌 **Steps:**
1. Use `find` to locate the password file:
   ```bash
   find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
   ```
2. Read the password:
   ```bash
   cat /var/lib/dpkg/info/bandit7.password
   ```
✅ **Password = morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj**

📝 **Challenges I Faced:**
- Got overwhelmed by `Permission denied` errors—learned to use `2>/dev/null` to silence them.
- Initially misinterpreted file size in bytes vs characters.

---

## Level 7 → 8: Extracting Data from a Large File
📌 **Steps:**
1. List the files:
   ```bash
   ls
   ```
   - This confirmed the existence of `data.txt`.
2. I initially used `cat data.txt`, but it was too long to manually search through.
3. Instead, I used:
   ```bash
   strings data.txt | grep "millionth"
   ```
   - `strings` filters out non-readable characters, and `grep` finds the line containing "millionth".
  
✅ **Password: dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc**

📝 **Challenges I Faced:**
- Initially, I tried manually searching with `cat`, which was ineffective due to the file's length.
- Realised `strings` is perfect for extracting human-readable text from binary-like files.

---

## Level 8 → 9: Finding the Unique Entry
📌 **Steps:**
1. Display the file contents:
   ```bash
   cat data.txt
   ```
2. Sort the file:
   ```bash
   sort data.txt
   ```
3. Identify the unique line:
   ```bash
   sort data.txt | uniq -u
   ```
✅ **Password = 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM**

📝 **Challenges I Faced:**
- Initially used `uniq data.txt` but it didn’t work because `uniq` only works on sorted input.
- Sorting first helped `uniq` to identify the truly unique line.

---

## Level 9 → 10: Finding the Password Pattern
📌 **Steps:**
1. Checked file contents with `cat`, which displayed a long output.
2. Instead of searching manually, used:
   ```bash
   strings data.txt | grep "="
   ```
✅ **Password = FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey**

📝 **Challenges I Faced:**
- Originally tried searching manually, which was inefficient.
- Learning to use `grep` with a keyword saved a lot of time.

---

## 🔡 Level 10 → 11: Decoding Base64
📌 **Steps:**
1. Checked the file contents:
   ```bash
   cat data.txt
   ```
   - The text was unreadable, hinting at encoding.
2. Used Base64 decoding:
   ```bash
   base64 -d data.txt
   ```
✅ **Password = dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr**

📝 **Challenges I Faced:**
- Initially puzzled by the unreadable text.
- Researching encoding types led me to Base64 decoding.

---

## Level 11 → 12: Decrypting ROT13
📌 **Steps:**
1. Examined the file:
   ```bash
   cat data.txt
   ```
2. Recognised the text was shifted.
3. Used the ROT13 decoding trick:
   ```bash
   cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
   ```
✅ **Password = 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4**

📝 **Challenges I Faced:**
- Initially didn’t know the encryption type.
- Learned about ROT13, a simple letter substitution cipher.

---

## Level 12 → 13: Unpacking Compressed Data
📌 **Steps:**
1. Extracted the hex dump:
   ```bash
   xxd -r data.txt > data
   ```
2. Used `file data` to check the format.
3. Iteratively decompressed using:
   ```bash
   tar, gzip, bzip2, and mv
   ```
✅ **Password = FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn**

📝 **Challenges I Faced:**
- Needed to research various compression methods.
- Trial-and-error approach helped in identifying the correct sequence of extractions.

---

## Level 13 → 14: SSH Private Key Authentication
📌 **Steps:**
1. Connected using SSH with the provided key:
   ```bash
   ssh -i sshkey.private bandit14@bandit.labs.overthewire.org -p 2220
   ```
✅ **Password = N/A**

📝 **Challenges I Faced:**
- Initially, SSH denied access due to incorrect permissions.
- Used `chmod 400 sshkey.private` to set the correct permissions.

---

## Level 14 → 15: Using Netcat
📌 **Steps:**
1. Connected via Netcat:
   ```bash
   nc localhost 30000
   ```
2. Entered the previous password, and received the new one.

✅ **Password = 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo**

📝 **Challenges I Faced:**
- Had never used `nc` before, so I had to read its manual.

---

## Level 15 → 16: Secure Netcat Connection
📌 **Steps:**
1. Used `ncat` for SSL support:
   ```bash
   ncat --ssl localhost 30001
   ```
✅ **Password = kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx**

📝 **Challenges I Faced:**
- Initially tried `nc`, but it lacked SSL support.

---

## Level 16 → 17: Scanning Ports with Nmap
📌 **Steps:**
1. Scanned for open ports:
   ```bash
   nmap -p 31000-32000 localhost
   ```
2. Connected to the correct port:
   ```bash
   ncat --ssl localhost 31790
   ```
✅ **SSH into the next level: ssh -i key bandit17@bandit.labs.overthewire.org**

📝 **Challenges I Faced:**
- Didn’t know which port was listening—`nmap` helped.

---

## Level 17 → 18: Comparing Files
📌 **Steps:**
1. Compared files using `diff`:
   ```bash
   diff passwords.new passwords.old
   ```
✅ **Password = ktfgBvpMzWKR5ENj26IbLGSblgUG9CzB**

📝 **Challenges I Faced:**
- Initially tried `cat` but couldn’t spot differences manually.

---

## Level 18 → 19: Running Bash Without Configuration
📌 **Steps:**
1. Bypassed restricted shell:
   ```bash
   ssh bandit18@bandit.labs.overthewire.org -p 2220 "bash --norc"
   ```
✅ **Password = cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8!**

📝 **Challenges I Faced:**
- Initially got kicked out instantly, but `--norc` solved it.

---

## Level 19 → 20: Using Set-UID Programs
📌 **Steps:**
1. Executed the special script:
   ```bash
   ./bandit20-do cat /etc/bandit_pass/bandit20
   ```
✅ **Password = 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO**

📝 **Challenges I Faced:**
- Learned about `setuid` programs and why they work with different user privileges.

---

## Level 20 → 21: Interacting with a Listening Port
📌 **Steps:**
1. **List available files in the home directory**
   ```bash
   ls
   ```
   - Found an executable file called `suconnect`.
   - This hinted that I needed to use it in some way.

2. **Understand the purpose of `suconnect`**
   ```bash
   ./suconnect
   ```
   - Running it without arguments returned a message, indicating that it expected a **port number**.
   
3. **Set up a listener in one terminal**
   - Opened a **new terminal** and logged back into Bandit 20.
   - Ran the following command to listen on port `1234`:
     ```bash
     nc -l -p 1234
     ```
   - This command tells `nc` (Netcat) to **listen** (`-l`) on **port 1234**.
   
4. **Send the password from one terminal to the other**
   - In the first terminal, I ran:
     ```bash
     ./suconnect 1234
     ```
   - This made `suconnect` connect to the **listening port (1234)** I set up earlier.
   - Upon successful connection, the password from Bandit 20 was sent over the network!
   
5. **Retrieve and store the password for Bandit 21**
   - The second terminal displayed the password, which I carefully copied:
     ```
     EeoULMCra2q0dSkYj561DX7s1CpBuOBt
     ```
✅ **Password = EeoULMCra2q0dSkYj561DX7s1CpBuOBt**

✅ **Password = cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8**

📝 **Challenges I Faced & Troubleshooting Steps:**
- **Issue:** Running `nc -l -p 1234` gave an error.
  - **Fix:** I realised that I needed to check if the port was already in use. Running `netstat -tulnp` helped confirm this.

- **Issue:** `suconnect` wasn’t sending anything.
  - **Fix:** I double-checked that I had entered the correct port number **in both terminals**.

- **Issue:** `nc` command didn’t work in some variations.
  - **Fix:** Used `ncat` instead: `ncat -l 1234` (on some systems, `nc` works differently).

---

This journey tested my patience and problem-solving skills. 🚀 **On to more challenges ahead!** 💻🔥


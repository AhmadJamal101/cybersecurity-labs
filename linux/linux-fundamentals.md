# Linux Fundamentals Notes

These are my Linux fundamentals notes from university, TryHackMe, and my own practice.

I’m using this file to keep track of the commands and concepts I practiced while building a stronger Linux foundation for cybersecurity and technical support.

---

## Terminal Basics

The Linux terminal is used to control the system by running commands.

Commands I practiced:

```bash
echo Hello
echo "Hello Friend!"
whoami
```

Notes:

- `echo` prints text to the terminal.
- `whoami` shows the current logged-in user.
- Quotation marks are useful when printing text that includes spaces.
- The terminal becomes easier with practice and repetition.

---

## Filesystem Navigation and Search

Linux uses files and directories to organize the system.

Commands I practiced:

```bash
ls
cd
find
grep
wc -l
```

Examples:

```bash
ls
find -name passwords.txt
find -name *.txt
grep "example" access.log
wc -l access.log
grep -R "PRETTY_NAME" /etc/
```

Notes:

- `ls` lists files and folders.
- `cd` changes the current directory.
- `find` searches for files by name.
- `grep` searches inside file contents.
- `wc -l` counts the number of lines in a file.
- `*` is a wildcard and means “anything”.
- `find -name *.txt` searches for `.txt` files.
- `grep -R` searches recursively inside folders.
- `Permission denied` means the current user does not have enough permission to access that file.

---

## Linux Operators

Operators help control how commands run and how output is handled.

Operators I practiced:

```bash
&
&&
>
>>
```

Notes:

- `&` runs a command in the background.
- `&&` runs the second command only if the first command succeeds.
- `>` redirects output to a file and overwrites the old content.
- `>>` redirects output to a file and adds new content at the end.

Examples:

```bash
echo hey > welcome
echo hello >> welcome
```

Important difference:

- `>` replaces the file content.
- `>>` adds to the file without deleting the old content.

---

## SSH and Remote Access

SSH stands for Secure Shell.

It is used to connect to a remote Linux machine from the terminal.

Basic format:

```bash
ssh username@IP
```

Example:

```bash
ssh user@10.10.10.10
```

Notes:

- SSH needs an IP address, username, and password.
- If the terminal asks to trust the host, type `yes`.
- Password input is invisible while typing, which is normal.
- After a successful login, the terminal prompt changes to show the remote user and machine.

Example prompt:

```bash
user@linux:~$
```

---

## Flags and Manual Pages

Flags are options added to commands to change how they work.

Examples:

```bash
ls -a
ls -lh
ls --help
man ls
```

Notes:

- Flags usually start with `-`.
- `ls -a` shows hidden files and folders.
- Hidden files usually start with `.`.
- `ls -lh` shows file sizes in a human-readable format.
- `--help` shows available options for a command.
- `man` opens the manual page for a command.
- Press `q` to exit a manual page.

---

## File and Folder Management

These commands are used to create, remove, copy, move, rename, and inspect files.

Commands I practiced:

```bash
touch
mkdir
rm
cp
mv
file
```

Examples:

```bash
touch note
mkdir mydirectory
rm note
rm -R mydirectory
cp note note2
mv note2 note3
file unknown1
```

Notes:

- `touch` creates a blank file.
- `mkdir` creates a directory.
- `rm` removes a file.
- `rm -R` removes a directory recursively.
- `cp` copies files or folders.
- `mv` moves or renames files and folders.
- `file` checks the type of a file.

Example output:

```text
unknown1: ASCII text
```

---

## File Permissions

Linux permissions control who can read, write, or execute files and directories.

Permission types:

```text
r = read
w = write
x = execute
```

Permission groups:

```text
Owner | Group | Others
```

Numeric values:

```text
r = 4
w = 2
x = 1
```

Examples:

```text
rwxrwxrwx = 777
rwxr-xr-x = 755
rw-r--r-- = 644
rwx------ = 700
```

Example command:

```bash
chmod 750 system_overview.txt
```

Meaning of `750`:

```text
Owner: read, write, execute
Group: read, execute
Others: no access
```

Notes:

- `r` allows reading.
- `w` allows writing or modifying.
- `x` allows execution.
- Permissions are applied separately to owner, group, and others.
- Numeric permissions are commonly used with `chmod`.

---

## Switching Users

Linux allows switching between users from the terminal.

Commands I practiced:

```bash
su user2
su -l user2
pwd
```

Notes:

- `su` switches to another user.
- `su -l` starts a login shell for the selected user.
- `pwd` shows the current working directory.
- Switching users requires the target user’s password.
- `su -l` gives a session closer to a real login as that user.

---

## Important Linux Directories

### `/etc`

`/etc` stores important system configuration files.

Examples:

```text
/etc/sudoers
/etc/passwd
/etc/shadow
```

Notes:

- `/etc/sudoers` controls which users and groups can run commands with sudo/root privileges.
- `/etc/passwd` stores user account information.
- `/etc/shadow` stores password-related information.

---

### `/var`

`/var` stores data that changes often.

Important path:

```text
/var/log
```

Notes:

- `/var` stores variable data used by services and applications.
- Logs are commonly stored in `/var/log`.
- This directory is useful when reviewing system or service activity.

---

### `/root`

`/root` is the home directory of the root user.

Note:

```text
/root
```

It is not:

```text
/home/root
```

---

### `/tmp`

`/tmp` stores temporary files.

Notes:

- `/tmp` is used for temporary data.
- It is commonly cleared after restart.
- Users can usually write files there.
- It is useful for temporary scripts, testing files, and lab practice.

---

## Commands Practiced

```bash
echo Hello
whoami
ls
ls -a
ls -lh
ls --help
man ls
find -name file.txt
grep "text" file.txt
grep -R "text" /path/
wc -l file.txt
touch note
mkdir mydirectory
rm note
rm -R mydirectory
cp note note2
mv note2 note3
file note
ssh user@IP
su user2
su -l user2
pwd
chmod 750 file.txt
```

---

## Key Takeaways

- The terminal is one of the main ways to control Linux.
- Linux commands become easier with practice.
- Flags change how commands behave.
- Manual pages are useful when I need to check command options.
- SSH is used to access remote Linux machines.
- Permissions are important for controlling access.
- Directories like `/etc`, `/var`, `/root`, and `/tmp` are important for understanding Linux system structure.
- Logs are commonly stored in `/var/log`.
- Temporary files are commonly stored in `/tmp`.

---

## Status

Linux Fundamentals: In Progress  
Current Focus: Building a stronger Linux command-line foundation for cybersecurity and technical support.

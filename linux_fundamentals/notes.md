# Linux Fundamentals Notes

**Author:** Your Name  
**Purpose:** Document my learning and practice of Linux fundamentals, including commands, file structures, permissions, and troubleshooting. This will serve as a reference I can revisit as I progress in my cybersecurity journey.

---

## Table of Contents
- [Overview](#overview)
- [Key Commands](#key-commands)
- [File System Structure](#file-system-structure)
- [Permissions and Ownership](#permissions-and-ownership)
- [Common Utilities & Tools](#common-utilities--tools)
- [Networking Basics in Linux](#networking-basics-in-linux)
- [Troubleshooting & Errors](#troubleshooting--errors)
- [Practical Exercises & Results](#practical-exercises--results)
- [Resources & References](#resources--references)
- [Reflections & Next Steps](#reflections--next-steps)

---

## Overview
**Date Started:** 2024-12-09  
In this section, I’m focusing on learning the basics of Linux. The goal is to understand how to navigate the file system, manage files and directories, understand permissions, and run basic network commands. This knowledge will later support more advanced cybersecurity work such as analyzing logs, running security tools, and setting up secure environments.

---

## Key Commands
**Commands Learned So Far:**

- `ls` - List directory contents.
  - `ls -l` shows permissions and ownership.
  - `ls -a` shows hidden files.
- `cd` - Change directory.
  - `cd ~` goes to the home directory.
- `pwd` - Print working directory.
- `cat`, `head`, `tail` - View file contents.
- `chmod`, `chown` - Modify file permissions and ownership.

*(As I learn more commands, I will add them here, along with brief usage notes.)*

---

## File System Structure
**Key Directories:**
- `/` - Root directory, everything starts here.
- `/home` - Contains user home directories.
- `/etc` - Configuration files for the system and services.
- `/var/log` - Log files live here, useful for troubleshooting and monitoring.
- `/usr/bin` and `/bin` - Where most user and system commands are stored.

*(Over time, I’ll add examples or notes on what files I’ve modified or viewed.)*

---

## Permissions and Ownership
**Date:** 2024-12-09

**Concepts:**
- Permissions are displayed as `rwx` triplets for user, group, and others.  
  Example: `-rw-r--r--` means:  
  - `r` (read) and `w` (write) for the owner.  
  - `r` (read) only for group.  
  - `r` (read) only for others.
- Changing permissions with `chmod`:  
  - `chmod u+x script.sh` gives the owner execute permission.
  - `chmod 755 script.sh` sets `rwxr-xr-x`.
- Ownership:  
  - `chown user:group filename` changes the owner and group of a file.

**Practical Example:**
- Created a script `test.sh` and ran `chmod +x test.sh` to make it executable.
- Verified execution by running `./test.sh` (assuming it’s a simple script that prints “Hello World”).

*(I’ll add more examples as I perform different permission changes or encounter related issues.)*

---

## Common Utilities & Tools
- **grep**: Search text within files.
  - Example: `grep "root" /etc/passwd` finds lines with the word “root” in `/etc/passwd`.
- **find**: Locate files and directories.
  - Example: `find / -name test.sh` searches the entire system for `test.sh`.
- **apt** or **yum**: Package managers for installing software (Ubuntu/Debian vs CentOS/RHEL).

---

## Networking Basics in Linux
Even though I’m focusing primarily on Linux fundamentals, I’ve started experimenting with a few networking commands:

- `ping`: Check connectivity to another host.
  - Example: `ping 8.8.8.8` tests connectivity to Google’s DNS server.
- `ifconfig` or `ip addr`: View network configuration.
- `curl`: Fetch data from URLs.
  - Example: `curl http://example.com` retrieves the homepage HTML.

*(As I learn more about networking in Linux, I’ll create a dedicated `networking_basics` folder or expand this section.)*

---

## Troubleshooting & Errors
**Date:** 2024-12-09  
**Issue:** Tried to `cat /etc/shadow` and received `Permission denied`.  
**Cause:** `/etc/shadow` stores hashed passwords and is restricted to root or privileged users.  
**Resolution:** Used `sudo` to view it as root, but generally, it’s best not to view this file unless necessary. This reinforced my understanding of system security measures.

*(Add more entries as I run into issues and solve them. Documenting how I fixed a problem will help me troubleshoot faster in the future.)*

---

## Practical Exercises & Results
**Exercise 1 (2024-12-09):**  
- Goal: Create a new user `testuser`, give them limited permissions, and experiment with file access.
- Steps:  
  1. `sudo adduser testuser`  
  2. `cd /home/testuser` and create `testfile.txt`.  
  3. `chmod 644 testfile.txt` to give read/write to owner and read-only to others.
- Result:  
  Logged in as `testuser` (via `su testuser`), confirmed they can read `testfile.txt`, but cannot edit files owned by `root` in `/etc`.

**Reflection:**  
This exercise taught me how user permissions and ownership limit what users can do, which is crucial for securing a system.

*(I’ll continue to add more exercises as I complete them. For example, future exercises might involve log analysis or using `grep` and `find` to locate critical files.)*

---

## Resources & References
- **HTB Academy Linux Fundamentals Module:** [Link to Module](#)
- **Official Ubuntu Documentation:** [https://help.ubuntu.com/](https://help.ubuntu.com/)
- **NIST SP 800-12 (Basics of Computer Security):** [https://csrc.nist.gov/publications](https://csrc.nist.gov/publications)
- **GitHub Awesome Linux:** [https://github.com/aleksandar-todorovic/awesome-linux](https://github.com/aleksandar-todorovic/awesome-linux)

*(As I encounter more resources, I’ll add them here. This creates a personal “library” of references.)*

---

## Reflections & Next Steps
**Current Skill Level:**  
I’m comfortable navigating directories, manipulating files, and understanding basic permissions. I still need more practice with advanced commands, scripting, and networking.

**Next Steps:**
- Practice more file permission scenarios (e.g., giving group members execute rights or removing read rights from others).
- Explore basic shell scripting (`bash`) to automate simple tasks.
- Move toward networking fundamentals next, using `ping`, `curl`, and eventually tools like `nmap`.

---

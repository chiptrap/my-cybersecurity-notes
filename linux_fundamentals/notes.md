# Linux Fundamentals Notes

**Author:** Bricen Chitty  
**Date:** 2024-12-05  
**Purpose:** To document foundational Linux knowledge, practices, and lessons learned as I progress in cybersecurity.

---

## Table of Contents
- [Overview](#overview)
- [Key Commands](#key-commands)
- [File System Structure](#file-system-structure)
- [Permissions & Ownership](#permissions--ownership)
- [Common Utilities & Tools](#common-utilities--tools)
- [Networking Basics in Linux](#networking-basics-in-linux)
- [Troubleshooting & Errors](#troubleshooting--errors)
- [Practical Exercises & Results](#practical-exercises--results)
- [Resources & References](#resources--references)
- [Reflections & Next Steps](#reflections--next-steps)

---

## Overview
Today I explored basic Linux navigation, focusing on understanding the directory structure and practicing fundamental commands to improve my system management skills. Building a strong foundation in these concepts will help me troubleshoot issues, secure servers, and prepare for more advanced security tasks in the future.

---

## Key Commands
- **`ls -l`**: Lists directory contents in long format, showing permissions, ownership, and file size.  
  -*Initial Note:* Running `ls -l /etc` helped me understand which files in the configuration directory are accessible or restricted, reinforcing my knowledge of file permissions.
- **`hostname`**: Print the name of the computer that we are logged into           
- **`whoami`**: Used on Windows  and Linux systems to get our current user name    
  -*Initial Note:* During a secuirty assessment we obtain reverse shell access on a host, and one of the first bits of situational awareness we should do is figuring out what user we are running as. From there, we can figure out if the user has any special privileges/access.
- **`Id`**: Expands on whoami. Print out our effective group memeberships and IDs. 
  -*Initial Note:* `adm` group means that the user can read log files in /var/log and could potentially gain access to sensitive information, membership in the `sudo` group is of particular interest as this means our user can run some or all commands as the all-powerful `root` user. 
- **`SSH [username]@[IP address]`**: Allows ssh connection to requested IP.        
- **`uname`**: Prints basic information about the operating system name and system hardware

---

## File System Structure
- **Root-Level Directories:**  
  For instance, `/etc` holds configuration files, `/var/log` contains logs, and `/home` hosts user directories. Understanding each directory’s purpose helps me know where to find critical files.
- *Note:* In a typical Linux environment, the local mail for a specific user is commonly stored in the user's mail spool file under the /var/mail/ directory.
- *Note:* A user's default shell is defined in the /etc/passwd file, listed as the last field in that user's entry.
  -It is commonly set to the Bourne Again Shell (bash) unless otherwise changed.
---

## Permissions & Ownership
- **`chmod 755 script.sh`**: Sets permissions so the owner can read, write, and execute, while group and others can read and execute.  
  *Initial Note:* Applying `chmod 755` to a test script allowed me to run it easily, while still limiting how others could interact with it.

---

## Common Utilities & Tools
- **`grep "error" /var/log/syslog`**: Quickly locates lines containing the word “error” in the system logs.  
  *Initial Note:* Using `grep` helped me identify recent authentication failures, providing insights into potential unauthorized access attempts.

--**`Secure Shell (SSH)`**: Protocol that allows clients to access and execute commands or actions on remote computers. SSH is one of the permanently installed standard tools and is the preferred choice for many administrators to configure and maintain a computer through remote access.
---

## Networking Basics in Linux
- **`ping 8.8.8.8`**: Tests network connectivity and latency.  
  *Initial Note:* Using `ping` confirmed my system’s ability to reach external DNS servers, which is essential for diagnosing internet connectivity issues.

---

## Troubleshooting & Errors
- **Issue:** Received `Permission denied` when trying to read `/etc/shadow`.  
  **Cause:** `/etc/shadow` is restricted to root for security reasons.  
  **Resolution:** Used `sudo cat /etc/shadow` to read it, understanding that strict permissions protect sensitive information.

*(If available, a screenshot of the error could be helpful, but is not required.)*

---

## Practical Exercises & Results
- **Exercise:** Created a new user `testuser` and tested their file access.  
  **Steps Taken:**  
  1. `sudo adduser testuser`  
  2. Placed a file in `/home/testuser` with `chmod 644 file.txt`  
  **Result:** Confirmed that `testuser` could read the file but not modify it, reinforcing my understanding of permission controls.

---

## Resources & References
- **HTB Academy Linux Fundamentals Module:**  
  [HTB Academy](https://academy.hackthebox.com/) - Guided labs and exercises.
- **Official Ubuntu Documentation:**  
  [Ubuntu Docs](https://help.ubuntu.com/) - In-depth OS references and best practices.
- **GNU Core Utilities Documentation:**  
  [GNU Manuals](https://www.gnu.org/manual/) - Comprehensive command documentation.
- **NIST SP 800-12:**  
  [NIST Publications](https://csrc.nist.gov/publications) - Foundational security guidelines.

---

## Reflections & Next Steps
After today’s work, I feel more comfortable navigating the file system, reading logs with `grep`, and adjusting file permissions. Moving forward, I plan to expand my skill set by exploring shell scripting, automating routine tasks, and delving deeper into network troubleshooting commands like `netstat` and `traceroute`.

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
  *Initial Note:* Running `ls -l /etc` helped me understand which files in the configuration directory are accessible or restricted, reinforcing my knowledge of file permissions.

---

## File System Structure
- **Root-Level Directories:**  
  For instance, `/etc` holds configuration files, `/var/log` contains logs, and `/home` hosts user directories. Understanding each directory’s purpose helps me know where to find critical files.

---

## Permissions & Ownership
- **`chmod 755 script.sh`**: Sets permissions so the owner can read, write, and execute, while group and others can read and execute.  
  *Initial Note:* Applying `chmod 755` to a test script allowed me to run it easily, while still limiting how others could interact with it.

---

## Common Utilities & Tools
- **`grep "error" /var/log/syslog`**: Quickly locates lines containing the word “error” in the system logs.  
  *Initial Note:* Using `grep` helped me identify recent authentication failures, providing insights into potential unauthorized access attempts.

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

# Linux Fundamentals Notes

## Table of Contents
- [Key Commands](#key-commands)
- [File System Structure](#file-system-structure)
- [Permissions and Ownership](#permissions-and-ownership)
- [Basic Networking Commands in Linux](#basic-networking-commands-in-linux)
- [Troubleshooting & Errors](#troubleshooting--errors)
- [Resources & References](#resources--references)

### Permissions and Ownership
**Date:** 2024-12-09  
- Learned the structure of Linux permissions: `rwx` for user, group, and others.
- `ls -l` displays permissions. For example: `-rw-r--r--` means owner can read/write, group and others can read only.
- `chmod`:  
  - `chmod u+x file.sh` adds execute permission for the user (owner).
  - `chmod 755 file.sh` sets `rwxr-xr-x`.

**Practical Exercise:**  
Created a script `test.sh`, ran `chmod +x test.sh`, verified execution with `./test.sh`.

**Reflections:**  
Understanding permissions is essential for securing files and limiting access. This ties into future security tasks like hardening systems.

# 5.2 🛠️ Creating Users and Groups (weight: 2)

**Weight:** 2  
**Description:** Creating users and groups on a Linux system.

---

## Key Knowledge Areas & Notes

### 👤 User and Group Commands
- **useradd**: Create a new user account. Default settings use `/etc/skel/` to populate home directory with template files.  
  - Example: `sudo useradd alice` → creates user without home directory by default.  
  - `sudo useradd -m bob` → creates user with a home directory `/home/bob`.  
  - Options:  
    - `-s /bin/bash` → specify default shell  
    - `-G group1,group2` → assign supplementary groups
- **groupadd**: Create a new group. Useful to manage permissions collectively.  
  - Example: `sudo groupadd developers` → creates a group named developers.  
- **passwd**: Set or change a user’s password. Only root or the user themselves can change it.  
  - Example: `sudo passwd alice` → prompts for new password.  
- 📝 Practice: Create several users with different shells, assign them to groups, and test password changes.

### 🆔 User IDs
- **UID**: Unique number identifying a user account.  
  - Root UID = 0 (full system access)  
  - Standard users: UID ≥ 1000 (default on most Linux distributions)  
  - System users: UID < 1000 (used by daemons/services, typically no login)  
- **GID**: Group ID of the primary group assigned to the user.  
- Practice: Check UID/GID using `id username` or view `/etc/passwd`.

### 📂 Partial List of Files, Terms, and Utilities
- **/etc/passwd**: Text file containing basic account info: username, UID, GID, home directory, and shell.  
- **/etc/shadow**: Contains encrypted password hashes and password aging info. Only root-readable 🔒  
- **/etc/group**: Defines groups and group memberships 👥  
- **/etc/skel/**: Skeleton directory; files here are copied to new user home directories.  
- **useradd**: Command to add a user.  
- **groupadd**: Command to add a group.  
- **passwd**: Command to set or update user passwords.  

### 💡 Additional Notes
- Always check created users in `/etc/passwd` and groups in `/etc/group`.  
- Assigning users to correct groups is essential for file and directory permission management.  
- New users inherit default files from `/etc/skel/` such as `.bashrc` and `.profile`.  
- Combine commands for efficiency:  
  ```bash
  sudo useradd -m -s /bin/bash -G developers testuser
  sudo passwd testuser

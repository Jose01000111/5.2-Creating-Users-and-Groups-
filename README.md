# 5.2 🛠️ Creating Users and Groups (weight: 2)

**Weight:** 2  
**Description:** Creating users and groups on a Linux system.

---

## Key Knowledge Areas & Notes

### 👤 User and Group Commands
- **useradd**: Create a new user, e.g., `sudo useradd alice`  
- Use `-m` to create a home directory: `sudo useradd -m bob`  
- **groupadd**: Create a new group, e.g., `sudo groupadd developers`  
- **passwd**: Set or change a user’s password, e.g., `sudo passwd alice`  
- 📝 Practice: Create users, assign passwords, and create groups

### 🆔 User IDs
- UID: Unique number identifying a user  
  - Root UID = 0  
  - Standard users: UID ≥ 1000  
  - System users: UID < 1000  
- GID: Group ID assigned to the user’s primary group  
- Practice: Check UID/GID with `id username`

### 📂 Partial List of Files, Terms, and Utilities
- **/etc/passwd**: Stores basic user info (username, UID, GID, shell)  
- **/etc/shadow**: Stores encrypted passwords 🔒  
- **/etc/group**: Stores group info and memberships 👥  
- **/etc/skel/**: Skeleton directory for new user home templates  
- **useradd**: Add a user  
- **groupadd**: Add a group  
- **passwd**: Set/change passwords

---

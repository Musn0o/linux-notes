**Linux File Permissions & Ownership Notes**

### **Understanding File Permissions**
Each file and directory in Linux has a **set of permissions** assigned to it, which determine who can **read (r)**, **write (w)**, or **execute (x)** it.

#### **Permission Format:**
A file's permissions are displayed as:
```bash
-rwxr--r--  1 user user 1234 Mar 22 10:00 file.txt
```
- First character (`-` or `d`): Indicates **file (-)** or **directory (d)**
- Next **3 characters** (`rwx`): **Owner’s** permissions
- Next **3 characters** (`r--`): **Group’s** permissions
- Last **3 characters** (`r--`): **Others'** permissions

#### **What Each Permission Means**
| Permission | File Meaning | Directory Meaning |
|------------|----------------------|-------------------------|
| **r (read)** | View file content | List directory (`ls`) |
| **w (write)** | Modify file content | Create/delete files in dir |
| **x (execute)** | Run as a program | Enter directory (`cd`) |

### **Changing Permissions with `chmod`**
#### **Symbolic Method:**
Modify permissions using `u` (user), `g` (group), `o` (others), `a` (all):
```bash
chmod u+x file.txt   # Give execute to user (owner)
chmod g-w file.txt   # Remove write from group
chmod o+r file.txt   # Allow others to read
chmod a+x script.sh  # Give execute to everyone
```

#### **Numeric Method:**
Each permission has a numeric value:
- `r` = **4**, `w` = **2**, `x` = **1**
- Sum them up to define permissions:
  - `rwx` (4+2+1) = **7**
  - `rw-` (4+2+0) = **6**
  - `r--` (4+0+0) = **4**

Examples:
```bash
chmod 755 script.sh  # Owner (rwx), Group (r-x), Others (r-x)
chmod 644 file.txt   # Owner (rw-), Group (r--), Others (r--)
chmod 600 private.txt  # Only owner can read/write
```

### **Changing Ownership with `chown`**
#### **Change File Owner:**
```bash
chown newuser file.txt
```
#### **Change Owner & Group:**
```bash
chown newuser:newgroup file.txt
```
#### **Change Ownership for a Directory & Its Contents:**
```bash
chown -R newuser:newgroup mydir/
```

### **Managing Users for Testing**
#### **Create a New User:**
```bash
sudo useradd testuser
```
#### **Switch to the New User:**
```bash
su - testuser
```
#### **Delete the User:**
```bash
sudo userdel testuser
```

### **Final Notes:**
- **Directories need `x` permission to `cd` into them.**
- **Scripts need `x` permission to execute (`chmod +x script.sh`).**
- **Use `ls -l` to check permissions of files.**
- **`chmod` for changing permissions, `chown` for changing ownership.**

✅ **Practice:** Try creating files, changing permissions, switching users, and experimenting with ownership! 🚀


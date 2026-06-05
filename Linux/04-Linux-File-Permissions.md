# Linux File Permissions and Ownership
Managing authorization is one of the key factors to insure security of an organisation. Security professionals ensure that the users must be authorized with appropriate permissions. This repository provides a comprehensive guide to understanding file permissions and ownership in Linux systems. It includes practical use of chmod and ls -al commands to change permissions on files.

### Types of File Permissions :

* **Read (r):** Allows viewing the contents of a file.
* **Write (w):** Allows modifying the contents of a file.
* **Execute (x):** Allows running a file (if it's a script or program) or accessing a directory's contents.
  
### Types of File Ownership
* **Owner:** The user who created the file.
* **Group:** A group of users who have shared access to the file.
* **Others:** All other users on the system.

### Permission representation : 
Permisiion includes 10 characters..> **drwxrwxrwx**
- **First character** : d represents the directory  - repersents file
- **2nd to 4th charcters** : write, read and execute permissions for user
- **5th to 7th charaters** : write, read and execute permissions for group
- **8th to 10th characters** : write, read and execute permissions for others
  
| Permission String | Type | Description |
|------------------|------|-------------|
| `drwxrwxrwx` | Directory | Owner, group, and others have read, write, and execute permissions. |
| `-rwxrwxrwx` | File | Owner, group, and others have read, write, and execute permissions. |
| `--wxrwxrwx` | File | Owner lacks read permission. |
| `---xrwxrwx` | File | Owner lacks read and write permissions. |
| `----rwxrwx` | File | Owner has no permissions. |
| `-----wxrwx` | File | Group lacks read permission. |
| `------xrwx` | File | Group lacks read and write permissions. |
| `-------rwx` | File | Group has no permissions. |
| `--------wx` | File | Others lack read permission. |
| `---------x` | File | Others lack read and write permissions. |
| `----------` | File | Others have no permissions. |




## chmod Command:
* Used to modify file permissions.
* Offers a symbolic or numeric mode to set permissions.
  **Symbolic Mode**: Uses letters and symbols to represent permissions and users.
u: User (owner)
g: Group
o: Others
a: All (user, group, and others)
+: Add permission
-: Remove permission
=: Set permission
   **example**
       input...>    chmod u-r,g+r drafts
       output..>    by using chmod u-x,o+x drafts command execute permission is removed from user and execute permission have added into group.
  
# ls -al Command:
* Lists files and directories in long format, displaying detailed information including permissions, ownership, size, and modification time. other than that it also shows hidden files with permissions.
  **example**
  drwx--x--- 2 researcher2 research_team 4096 Jan  8 22:51 drafts
                   drwx--x---: File permissions
                            2: Number of hard links
                 researcher2 : Owner
                research_team: Group
                         4096: File size in bytes
                  jan 8 22:51: Last modified date and time
                       drafts: Filename

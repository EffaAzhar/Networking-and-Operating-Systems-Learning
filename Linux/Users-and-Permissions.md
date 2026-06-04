## Linux Users, Privileges, and Sudo

Linux follows the principle of least privilege. Regular users have limited permissions while administrative tasks require elevated privileges. `sudo` command provides these elevated privileges.
### Accessing Protected Files

The `/etc/sudoers` file controls which users are allowed to execute commands with elevated privileges.
Attempting to view the file without sufficient permissions results in an error:

```bash
cat /etc/sudoers
```

Output:

```text
Permission denied
```

To access the file, administrative privileges are required:

```bash
sudo cat /etc/sudoers
```

![Linux Sudoers File](screenshots/linux-view-sudoers-file.png)
**Figure 1:** Viewing the `/etc/sudoers` file using elevated privileges.

### Switching to the Root Account

A user with sudo privileges can temporarily become the root user:

```bash
sudo su -
```

After authentication, the prompt changes:

```text
root@ubuntu-vm:~#
```

This indicates that commands are now being executed with full administrative privileges. it is not a good approoach to stay logged in as root all the time. ​There are lots of critical services and files that can be mistakenly changed. Therefore, we use `exit` command to logout.

![Linux Sudo Group and Root Access](screenshots/linux-sudo-group-and-root-access.png)

**Figure 2:** Members of the sudo group can execute administrative commands and switch to the root account.

### Cybersecurity Relevance

Privilege management is a critical security concept. Proper use of sudo can help in:

* Reduce unnecessary root usage.
* Limit administrative access.
* Improve accountability through logging.
* Support the principle of least privilege.
* Reduce the impact of accidental or malicious changes.

## Viewing Linux Groups

Linux stores group information in the `/etc/group` file.

The following command displays all groups configured on the linux system:

```bash
cat /etc/group
```

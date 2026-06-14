 # Linux Process Management 

Linux manages every running program as a process. Each process is assigned a unique Process ID (PID) and is managed by the Linux kernel. Understanding process management is essential for system administration, troubleshooting, performance monitoring and cybersecurity investigations. When you start up your computer, ​the kernel creates a process called **init** ​which has a PID of one. ​init starts up other processes ​that we need to get our computer up and running. During this lab, I explored process listing commands, parent-child process relationships, the Linux init process and the `/proc` filesystem.

## Understanding the Init Process

The first user-space process started by the Linux kernel during system boot is known as the **Init Process**.

Traditionally Linux used:

```bash
/sbin/init
```

Modern Linux distributions such as Ubuntu use:

```bash
systemd
```
It is responsible for following,

* Starting system services during boot
* Managing background daemons
* Handling service dependencies
* Adopting orphaned processes
* Coordinating system shutdown and reboot


## Viewing User Processes with `ps -x`

The `ps -x` command displays processes owned by the current user it also includes those processes that are not attached to a terminal session.

```bash
ps -x
```

### Screenshot

![Linux ps x Output](screenshots/linux-ps-x-process-list.png)

- Every running application is represented as a process.
- Each process has a unique PID.
- The `STAT` column shows the process state. Type of process status are following **R** for running it means the process is running or it's waiting to run. **T** for stopped meaning a process that's been suspended **S** S for interruptible sleep Meaning the task is waiting for an event ​to complete before it resumes
- The `COMMAND` column shows the  command being run.
- Many desktop environment services run in the background even when no applications are actively open.


## Viewing All Processes with `ps -ef`

The `ps -ef` command displays all processes currently running on the system. The **-e flag** is used to get all processes, ​even the ones run by other users. ​The **-f flag** is for full, ​which shows you full details about ​a process.

```bash
ps -ef
```

### Screenshot

![Linux ps ef Output](screenshots/linux-ps-ef-process-tree.png)

### Important Columns

| Column | Description |
|----------|-------------|
| UID | User that owns the process |
| PID | Process ID |
| PPID | Parent Process ID |
| CMD | Command used to start the process |
|S   | time is the start time of the process|
|​TTY |the terminal associated with the process|
|​Time | total CPU time that the process has taken up|

- Every process has a parent process.
- Linux uses a hierarchical process structure.
- PID 1 is typically assigned to `systemd`.
- `systemd` is responsible for starting many services during system boot.


## Searching for Processes

Processes can be searched using `grep`.

```bash
ps -ef | grep chrome
```

### Screenshot

![Searching Processes](screenshots/linux-grep-process-search.png)

- `grep` filters process output.
- Useful for checking if a service or application is running.
- If the application is not running, only the `grep` process may appear.



## Exploring the `/proc` Filesystem

Everything in Linux is a file, even processes. ​To view the files that correspond to processes, ​we can look into the slash proc directory. ​There are a lot of directories here ​for every process that is running. ​If you look inside one of the subdirectories, ​it will  give more information about the process. Linux exposes process information through the virtual `/proc` filesystem.

```bash
ls -l /proc
```

### Screenshot

![Linux Proc Filesystem](screenshots/linux-proc-filesystem-processes.png)

### What I Learned

The numbered directories represent active process IDs.

Examples:

```text
/proc/1
/proc/2503
/proc/3980
```

Each process directory contains information about that specific process. This allows administrators to inspect running processes directly through the filesystem.
Useful files include:

```text
/proc/<PID>/status
/proc/<PID>/cmdline
/proc/<PID>/fd
/proc/<PID>/maps
```




## Process IDs (PID)

Every process receives a unique Process ID.

Example:

```text
3980 = bash
```

The PID can be used to:

- Monitor processes
- Kill processes
- Investigate process behaviour


## Parent Process IDs (PPID)

Every process is created by another process.

Example:

```text
PPID 1 → systemd
PPID 3980 → bash
```

This relationship forms a process tree that shows how applications are launched and managed.


## Common Process States

| State | Meaning |
|---------|---------|
| R | Running |
| S | Sleeping |
| D | Uninterruptible Sleep |
| T | Stopped |
| Z | Zombie |



## Commands Practiced

```bash
ps -x
ps -ef
ps -ef | grep chrome
ls -l /proc
```



## Key Takeaways

- Linux manages applications as processes.
- Each process receives a unique PID.
- Processes are organized in parent-child relationships.
- `systemd` acts as the primary process manager.
- The `/proc` filesystem exposes process information.
- `ps` and `grep` are essential tools for monitoring and troubleshooting running processes.


# Linux Package Management with dpkg

Linux distributions use package management systems to install, update, and remove software. Ubuntu commonly distributes software using .deb packages. These packages are used to install software after which the program files are extracted into various system directories. A `.deb` file contains:

- Program files
- Configuration files
- Dependency information
- Installation scripts

## `dpkg` Command

`dpkg` is the low-level package manager used by Debian-based Linux distributions.

It can:

- Install packages
- Remove packages
- List installed packages
- Display package information

### Listing Installed Packages

```bash
dpkg -l
```
The screenshot below shows installed packages on my Ubuntu VM.

![Installed Packages](screenshots/linux-dpkg-list-packages.png)

*Figure 1: Listing installed packages using the `dpkg -l` command.*

### Installing a Package

To install a package we use flag `-i`. 
```bash
sudo dpkg -i package_name.deb
```

Example:

```bash
sudo dpkg -i vscode.deb
```

### Removing a Package

To remove an installed package we usr `-r` flag.

```bash
sudo dpkg -r package_name
```

Example:

```bash
sudo dpkg -r nginx
```


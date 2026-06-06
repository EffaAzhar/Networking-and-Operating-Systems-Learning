# Windows Package Management

Package management refers to the process of installing, updating and removing software from a system. Windows provides several methods for managing software, including graphical installers and command-line tools.

Common software installation files in Windows include:

```text
.exe
.msi
```

### EXE Installers

Executable (`.exe`) files are the most common installation packages used in Windows. EXE installers typically provide a setup wizard that guides users through the installation process.

Examples:

```text
ChromeSetup.exe
VSCodeSetup.exe
Wireshark.exe
```

### MSI Installers

MSI (Microsoft Installer) files provide a standardized installation format for Windows applications. MSI packages are commonly used in enterprise environments because they support automated deployment and management.
For Example:
```text
Wireshark.msi
ZoomInstaller.msi
``` 
## `Winget` command

Windows Package Manager (Winget) is a command-line tool used to install, update and remove software.

#### Display Installed Software

```powershell
winget list
```

Displays software currently installed on the system.

![Winget List](screenshots/windows-winget-list.png)

*Figure 1: Displaying installed software using the `winget list` command.*


#### Search for Software

```powershell
winget search vscode
```

Searches for software packages available in the Winget repository.

![Winget Search](screenshots/windows-winget-search.png)

*Figure 2: Searching for available software packages using Winget.*

#### Install Software

```powershell
winget install Microsoft.VisualStudioCode
```

Installs Visual Studio Code.

![Winget Install](screenshots/windows-winget-install.png)

*Figure 3: Installing software using the `winget install` command.*


#### Remove Software

```powershell
winget uninstall Microsoft.VisualStudioCode
```

Removes Visual Studio Code from the system.



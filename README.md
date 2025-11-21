# Windows Dotfiles

This repository contains my configuration files (dotfiles) for Windows, managed using [Dotbot](https://github.com/anishathalye/dotbot).

## Managed Configurations

- **Komorebi** (Tiling Window Manager)
- **whkd** (HotKey Daemon)
- **yasb** (Status Bar)
- **Windows Terminal**

## Prerequisites

Before installing, ensure you have the following installed:

1.  **Git**
2.  **Python** (Required to run Dotbot)
3.  **PowerShell** (Must be run with **Administrator privileges** to create symbolic links)

> **Note:** This setup only links configuration files. You must install the actual applications (komorebi, yasb, etc.) separately using `winget` or `scoop`.

## Installation

### 1. Clone the Repository

Since this repository uses Dotbot as a git submodule, you must clone it with the `--recursive` flag.

```powershell
# Clone to your desired location
git clone --recursive [https://github.com/](https://github.com/)<YOUR_USERNAME>/windows-dotfiles.git

# Enter the directory
cd windows-dotfiles
```

**If you have already cloned the repo without the submodule:**

```powershell
git submodule update --init --recursive
```

### 2. Run the Installer

Open **PowerShell as Administrator** and run the installation script. This will create the necessary symbolic links.

```powershell
# Run the install script
.\install.ps1
```

If successful, your config files will be linked to `~/.config/` and `AppData` directories.

## Updating

To update your dotfiles and apply changes:

```powershell
# 1. Pull the latest changes
git pull

# 2. Update the Dotbot submodule (optional, but recommended)
git submodule update --remote

# 3. Re-run the installer to apply new links
.\install.ps1
```

## Troubleshooting

### Execution Policy Error

If you receive a permission error when running the script, change the execution policy temporarily:

```powershell
Set-ExecutionPolicy RemoteSigned -Scope Process
```

### Symbolic Link Errors

If you see "Linking failed" or permission errors:

- Ensure you are running PowerShell as **Administrator**.
- Windows requires admin rights to create symlinks by default.

## Windows Autostart Memo

[komorebi + whkd]

1. Open PowerShell or Command Prompt.
2. Run the following command:
   komorebic enable-autostart --whkd
3. (To disable it later, run: komorebic disable-autostart)

---

[yasb]

1. Open PowerShell or Command Prompt.
2. Run the following command:
   yasbc enable-autostart
3. (To disable it later, run: yasbc disable-autostart)

## App List

- komorebi + whkd
- yasb
- winfetch
- bottom

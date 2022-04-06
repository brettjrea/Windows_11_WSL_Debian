---
title: WSLg_Debian
layout: repos
permalink: /WSLg_Debian/
repository_weight: 2
---

# Windows_11_WSLg_Debian

---

<details>
<summary>Overview</summary>
  
The third tool in the modern developer toolbox is an instance of linux to run some useful scripts and services on. Developers used to need to either dual boot there machines have a seperate machine, or create memory hogging virtual machines. In recent times though we have advanced technologies like Docker and the Windows Subsystem for Linux. These tools allow for slimmer services that share the local operating system where it can, and reduce the amount of memory overhead. Although I enjoy using Docker there is a learning curve if you want to write your own docker compose files, for this reason I recommend using Windows Subsytem for Linux in the past I have used the Canonical sponsored Ubuntu 18.04 LTS 'Bionic' but recently the pure opensource parent distro Debian 10 LTS 'Buster' released and I find its package repository has more up to date versions of some common tools like NPM, NodeJS, and PHP. The package repository is purely open source and you can get MySql installed but the MySql fork MariaDb is a perfect opensource drop in replacement from the same creator. If this all sounds good to you below is a how-to on Enabling WSL, Downloading, Installing, launching and Upgrading Debian all from the Windows Powershell.

</details>

---

### 1. Open Windows Powershell from powerusers menu.

Press <kbd>WIN</kbd>+<kbd>X</kbd> then <kbd>A</kbd> to open Windows Powershell (Admin) from powerusers menu.

Press <kbd>ALT</kbd>+<kbd>Y</kbd> to select <kbd>Yes</kbd> at the UAC prompt.

---

### 2. Enable Windows Optional Feature Microsoft-Windows-Subsystem-Linux.

Copy the following with <kbd>CTRL</kbd>+<kbd>C</kbd>

```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

and paste into Powershell with <kbd>Right Mouse Click</kbd> and press <kbd>Enter</kbd>

---
### Enable Hyper-V.

```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V -All
```
```
wsl --set-default-version 2
```
```
Invoke-WebRequest -Uri https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi -OutFile wsl_update_x64.msi -UseBasicParsing
```
```
.\wsl_update_x64.msi
```

### 3. Download Debian.

Copy the following with <kbd>CTRL</kbd>+<kbd>C</kbd>

```
Invoke-WebRequest -Uri https://aka.ms/wsl-debian-gnulinux -OutFile debian.appx -UseBasicParsing
```

and paste into Powershell with <kbd>Right Mouse Click</kbd> and press <kbd>Enter</kbd>

---

### 4. Add Debian package.

Copy the following with <kbd>CTRL</kbd>+<kbd>C</kbd>

```Add-AppxPackage .\debian.appx```

and paste into Powershell with <kbd>Right Mouse Click</kbd> and press <kbd>Enter</kbd>

---

### 5. Start Debian.

Type into Windows Powershell:

`debian` 

and press <kbd>Enter</kbd>

---

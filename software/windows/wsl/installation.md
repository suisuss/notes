

#### Install Docker Windows 10 + 11

**Requirements:**

#### Instructions

- `wsl --install`
- Enable the Windows Subsystem for Linux
  - `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
- Enable Virtual Machine feature
  - `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
- Download the Linux kernel update package
  - [x64](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
- Set WSL 2 as your default version
  - `wsl --set-default-version 2`
- Install your Linux distribution
  - [Microsoft Store](https://aka.ms/wslstore)
    - Ubuntu 18.04 LTS
    - Ubuntu 20.04 LTS
    - openSUSE Leap 15.1
    - SUSE Linux Enterprise Server 12 SP5
    - SUSE Linux Enterprise Server 15 SP1
    - Kali Linux
    - Debian GNU/Linux
    - Fedora Remix for WSL
    - Pengwin
    - Pengwin Enterprise
    - Alpine WSL

#### Problems

**WslRegisterDistribution Error:**

When running your distro program for the first time it will go through a installation process that can result in this error.

- 0x80370102
  - Make sure hardware virtualization is enabled via BIOS

#### Resources

- [https://www.windowscentral.com/how-install-wsl2-windows-10](https://www.windowscentral.com/how-install-wsl2-windows-10)
- [https://docs.microsoft.com/en-gb/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package](https://docs.microsoft.com/en-gb/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package)
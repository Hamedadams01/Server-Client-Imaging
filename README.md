## Windows Server 2019 & Windows 11 Lab Build — Imaging Project

# Overview

A hands-on lab build using Oracle VirtualBox: a Windows Server 2019 domain controller ("Houtech") and a Windows 11 client, set up from scratch as the foundation for Active Directory practice.

# Objectives

- Organize Windows Server 2019 and Windows 11 installation files in a central, easy-to-access location
- Create Remote Desktop shortcuts for quick reconnection to each VM
- Build a Windows Server 2019 VM in VirtualBox to serve as a domain controller
- Successfully install and configure Windows Server 2019 (Standard Evaluation, Desktop Experience)
- Rename the server host to a meaningful, recognizable name ("Houtech")
- Build a Windows 11 VM in VirtualBox to serve as a client machine
- Successfully install and configure Windows 11 through the full OOBE (Out-of-Box Experience) flow
- Prepare both VMs to be joined together for future Active Directory testing


# Process

1. Organizing Lab Assets

Created a dedicated OneDrive folder ("Imageing") to store the Windows Server 2019 and Windows 11 ISO/install files. Created two Remote Desktop Connection (.rdp) shortcut files, Windows11 and Server25, pre-configured to connect to each VM's hostname/IP once built.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-06%20094743.png?raw=true)

2. Creating the Server 19 VM

In Oracle VirtualBox, ran the New Virtual Machine wizard: VM name "Server 19," OS type Microsoft Windows, OS Version Windows Server 2019 (64-bit), VM storage path set to C:\Users\hamed\VirtualBox VMs. No ISO attached at this stage.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20101557.png?raw=true)

3. Fixing "No Bootable Medium"

Powered on the VM and hit a boot failure: "No bootable medium found. Please insert a bootable medium and reboot." Used the VirtualBox prompt to mount the Windows Server 2019 evaluation ISO to the virtual DVD drive and selected "Mount and Retry Boot."

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20102126.png?raw=true)

4. Launching Setup

VM booted from the mounted ISO into the Windows Server 2019 Setup splash screen and clicked "Install now" to start the installer.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20102153.png?raw=true)

5. Choosing the Edition

Setup listed four available editions: Standard Evaluation, Standard Evaluation (Desktop Experience), Datacenter Evaluation, and Datacenter Evaluation (Desktop Experience). Selected Windows Server 2019 Standard Evaluation (Desktop Experience) — the full GUI build (not Server Core) — and clicked Next.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20102209.png?raw=true)

6. Selecting the Install Disk

On the "Where do you want to install Windows?" screen, selected Drive 0 Unallocated Space (30.0 GB total/free) as the target partition and proceeded with setup.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20102227.png?raw=true
)

7. Setting the Admin Password

After the file-copy phase, the "Customize settings" screen prompted for a password on the built-in Administrator account. Entered and confirmed the password.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20102719.png?raw=true)

8. Confirming Install Success

VM rebooted and landed on the Windows lock screen ("Press Ctrl+Alt+Delete to unlock"), confirming a completed install with no setup errors.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20102803.png?raw=true)

9. Renaming the Server

Signed in, opened Settings > System > About, and used "Rename this PC." Default computer name was the auto-generated WIN-VUM9M3UPG7L.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20103216.png?raw=true)
10. Verifying Server Specs

Confirmed the device name updated to Houtech and reviewed the system specs to verify the build.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-21%20103534.png?raw=true
)
11. Creating the Windows 11 VM

Repeated the VirtualBox New Virtual Machine wizard: VM name "Window 11 lab," OS type Microsoft Windows, OS Version Windows 11 (64-bit), stored in the same local VirtualBox VMs directory.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20054841.png?raw=true)

12. Mounting Windows 11 Media

Same "failed to boot" error on first power-on. Mounted the downloaded ISO Win11_25H2_English_x64.iso from the local Downloads folder and selected "Mount and Retry Boot."

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20055012.png?raw=true)

13. Setting Language/Region

Windows 11 Setup wizard opened to "Select language settings." Set Language to install and Time/currency format both to English (United States), then clicked Next.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20055051.png?raw=true)

14. Choosing Setup Option

On "Select setup option," chose "Install Windows 11" and checked the box acknowledging all files, apps, and settings on the target disk would be deleted (disk was new/unallocated, so no data loss).

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20055107.png?raw=true)

15. Selecting Install Location

On "Select location to install Windows 11," selected Disk 0 Unallocated Space (60.0 GB total/free) as the target partition.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20055145.png?raw=true)
16. Choosing Region in OOBE

After file copy and reboot, the Windows 11 OOBE prompted for a country/region from a scrollable list. Selected "United States."

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20060059.png?raw=true)

17. Signing In with a Microsoft Account

OOBE presented the "Let's add your Microsoft account" sign-in screen (standard consumer setup flow, same as a retail PC).

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20070404.png?raw=true)

18. Reviewing the Backup Restore Option

Windows detected the linked Microsoft account and displayed a "Welcome back" screen offering to restore a prior device backup labeled HOUTX01 (last backup: June 21, 2026), covering Folders, Apps, Settings, and Credentials. Reviewed the option without restoring.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20070648.png?raw=true)

19. Verifying the Finished Build

Reached the desktop, opened the Start menu, and confirmed a signed-in profile with an active taskbar clock — confirming a fully functional, ready-to-domain-join client build.

![image alt](https://github.com/Hamedadams01/Server-Client-Imaging/blob/main/Screenshot%202026-06-22%20071123.png?raw=true)

Imaging Project

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
![image alt]()
Created a dedicated OneDrive folder ("Imageing") to store the Windows Server 2019 and Windows 11 ISO/install files. Created two Remote Desktop Connection (.rdp) shortcut files, Windows11 and Server25, pre-configured to connect to each VM's hostname/IP once built.

2. Creating the Server 19 VM
![image alt]()
In Oracle VirtualBox, ran the New Virtual Machine wizard: VM name "Server 19," OS type Microsoft Windows, OS Version Windows Server 2019 (64-bit), VM storage path set to C:\Users\hamed\VirtualBox VMs. No ISO attached at this stage.

3. Fixing "No Bootable Medium"
![image alt]()
Powered on the VM and hit a boot failure: "No bootable medium found. Please insert a bootable medium and reboot." Used the VirtualBox prompt to mount the Windows Server 2019 evaluation ISO to the virtual DVD drive and selected "Mount and Retry Boot."
![image alt]()
4. Launching Setup
![image alt]()
VM booted from the mounted ISO into the Windows Server 2019 Setup splash screen and clicked "Install now" to start the installer.
![image alt]()
5. Choosing the Edition
![image alt]()
Setup listed four available editions: Standard Evaluation, Standard Evaluation (Desktop Experience), Datacenter Evaluation, and Datacenter Evaluation (Desktop Experience). Selected Windows Server 2019 Standard Evaluation (Desktop Experience) — the full GUI build (not Server Core) — and clicked Next.

6. Selecting the Install Disk
![image alt]()
On the "Where do you want to install Windows?" screen, selected Drive 0 Unallocated Space (30.0 GB total/free) as the target partition and proceeded with setup.

7. Setting the Admin Password
![image alt]()
After the file-copy phase, the "Customize settings" screen prompted for a password on the built-in Administrator account. Entered and confirmed the password.

8. Confirming Install Success
![image alt]()
VM rebooted and landed on the Windows lock screen ("Press Ctrl+Alt+Delete to unlock"), confirming a completed install with no setup errors.

9. Renaming the Server
![image alt]()
Signed in, opened Settings > System > About, and used "Rename this PC." Default computer name was the auto-generated WIN-VUM9M3UPG7L.

10. Verifying Server Specs
![image alt]()
Confirmed the device name updated to Houtech and reviewed the system specs to verify the build.

11. Creating the Windows 11 VM
![image alt]()
Repeated the VirtualBox New Virtual Machine wizard: VM name "Window 11 lab," OS type Microsoft Windows, OS Version Windows 11 (64-bit), stored in the same local VirtualBox VMs directory.

12. Mounting Windows 11 Media
![image alt]()
Same "failed to boot" error on first power-on. Mounted the downloaded ISO Win11_25H2_English_x64.iso from the local Downloads folder and selected "Mount and Retry Boot."

13. Setting Language/Region
![image alt]()
Windows 11 Setup wizard opened to "Select language settings." Set Language to install and Time/currency format both to English (United States), then clicked Next.

14. Choosing Setup Option
![image alt]()
On "Select setup option," chose "Install Windows 11" and checked the box acknowledging all files, apps, and settings on the target disk would be deleted (disk was new/unallocated, so no data loss).

15. Selecting Install Location
![image alt]()
On "Select location to install Windows 11," selected Disk 0 Unallocated Space (60.0 GB total/free) as the target partition.

16. Choosing Region in OOBE
![image alt]()
After file copy and reboot, the Windows 11 OOBE prompted for a country/region from a scrollable list. Selected "United States."

17. Signing In with a Microsoft Account
![image alt]()
OOBE presented the "Let's add your Microsoft account" sign-in screen (standard consumer setup flow, same as a retail PC).

18. Reviewing the Backup Restore Option
![image alt]()
Windows detected the linked Microsoft account and displayed a "Welcome back" screen offering to restore a prior device backup labeled HOUTX01 (last backup: June 21, 2026), covering Folders, Apps, Settings, and Credentials. Reviewed the option without restoring.

19. Verifying the Finished Build
![image alt]()
Reached the desktop, opened the Start menu, and confirmed a signed-in profile with an active taskbar clock — confirming a fully functional, ready-to-domain-join client build.

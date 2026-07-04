# Server-ClProject 1: Server & Client Imaging (VirtualBox Lab Build)
Overview
This project covers building the two core machines for the Houtech.local lab — a Windows Server 2019 domain controller and a Windows 11 client — from scratch in Oracle VirtualBox, from ISO download through first sign-in.
Objectives

Set up organized local storage for Windows Server 2019 and Windows 11 install media
Build a Windows Server 2019 VM to serve as the domain controller
Build a Windows 11 VM to serve as a client endpoint
Prepare both machines for later Active Directory domain join

Step-by-Step

I organized my Windows Server 2019 and Windows 11 installation files in a dedicated OneDrive folder and created Remote Desktop shortcuts (Windows11, Server25) for quick reconnects later.
I created a new VM named "Server 19" in VirtualBox, setting the OS to Windows Server 2019 (64-bit) and pointing it to my local VirtualBox VMs directory.
I hit a "No bootable medium found" error on first boot, so I mounted the Windows Server 2019 evaluation ISO and retried.
I clicked "Install now" on the Windows Setup screen to begin installation.
I selected "Windows Server 2019 Standard Evaluation (Desktop Experience)" so I'd have a GUI for managing AD roles.
I selected the 30 GB unallocated disk as the install target.
I set a secure Administrator password when prompted after the file copy finished.
I confirmed the VM rebooted to the Windows lock screen, verifying the install completed.
I signed in and renamed the PC from the default auto-generated name to "Houtech."
I confirmed the rename took effect and reviewed the specs (Intel i5-7500, 2.00 GB RAM, 64-bit) to verify readiness as the domain controller.
I created a second VM, "Window 11 lab," setting the OS to Windows 11 (64-bit).
I hit the same "no bootable medium" issue, mounted my Windows 11 25H2 ISO, and retried the boot.
I confirmed the language and time/currency format as English (United States) on Windows 11 Setup.
I selected "Install Windows 11" and accepted the file-deletion warning since the disk was brand new.
I selected the 60 GB unallocated disk as the install location.
I selected "United States" as my region during the out-of-box experience.
I signed in with a Microsoft account to proceed through the standard OOBE flow.
I reviewed the PC backup restore screen (device "HOUTX01") to understand what end users see during setup — useful context for troubleshooting sign-in/profile issues later.
I reached the desktop and opened the Start menu, confirming Windows 11 was fully installed and signed in as "hamed adams."

Conclusion

Both VMs were built successfully and are functional
Server 19 was renamed to "Houtech" and is ready to be promoted to a domain controller
The Windows 11 client is ready to be joined to the Houtech domain
This sets up the environment for the next phase: Active Directory configurationient-Imaging

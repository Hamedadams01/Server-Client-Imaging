## Server-ClProject 1: Server & Client Imaging (VirtualBox Lab Build)

# Overview
Before any Active Directory work could begin, I needed a working domain controller and a working client machine. This project documents building both from the ground up in Oracle VirtualBox — sourcing install media, provisioning virtual hardware, running through Windows Server 2019 and Windows 11 setup, and confirming both machines were healthy and ready to be joined together. This is the foundation every later project (AD, GPOs, domain join) depends on.

# Objectives
- Organize installation media so builds are repeatable and not scattered across folders
- Provision a Windows Server 2019 VM to serve as the future domain controller
- Provision a Windows 11 VM to serve as a domain-joinable client
- Resolve boot/media errors as they came up rather than starting over
- Rename and verify both machines so they're recognizable throughout the rest of the lab

## Step-by-Step
# Setting up install media

I organized my Windows Server 2019 and Windows 11 installation files in a dedicated OneDrive folder ("Imageing") and created Remote Desktop shortcuts (Windows11, Server25) so I could reconnect to either machine quickly once built.
# Building the domain controller (Server 19)

- I created a new VM named "Server 19" in VirtualBox, setting the OS type to Windows Server 2019 (64-bit) and pointing it to my local VirtualBox VMs directory.
- I hit a "No bootable medium found" error on first power-on because no ISO was mounted yet — I mounted the Windows Server 2019 evaluation ISO and retried the boot.
- I clicked "Install now" on the Windows Setup screen to begin installation.
- I selected "Windows Server 2019 Standard Evaluation (Desktop Experience)" specifically for the GUI, since I'd need to manage AD roles visually and wanted the lab to look presentable in a portfolio.
- I selected the 30 GB unallocated disk as the install target.
- I set a secure Administrator password once the file copy finished, since this account would have full control over the machine on first boot.
- I confirmed the VM rebooted successfully to the Windows lock screen, verifying the install had completed cleanly.
- I signed in and renamed the PC from its default auto-generated name to "Houtech" — a meaningful hostname the domain would later be built around.
- I reviewed the renamed machine's specs (Intel i5-7500, 2.00 GB RAM, 64-bit OS) to confirm it was configured correctly and ready to serve as the domain controller referenced throughout the rest of the lab.
# Building the client (Windows 11)

- I created a second VM, "Window 11 lab," setting the OS to Windows 11 (64-bit).
- I hit the same "no bootable medium" error, mounted my Windows 11 25H2 ISO, and retried the boot.
- I confirmed the language and time/currency format as English (United States) on the Windows 11 Setup screen.
- I selected "Install Windows 11" and accepted the file-deletion warning, since the virtual disk was brand new and unallocated.
- I selected the 60 GB unallocated disk as the install location.
- I selected "United States" as my region during the out-of-box experience (OOBE) to keep locale settings consistent with the rest of the lab.
- I signed in with a Microsoft account to proceed through the standard OOBE flow — the same experience a real end user would go through.
- I reviewed the PC backup restore screen (device "HOUTX01") that Windows offered during setup, noting what an end user sees at this stage — useful context for later helpdesk troubleshooting around profile restores and sign-in issues.
- I reached the desktop and opened the Start menu, confirming Windows 11 was fully installed and signed in as "hamed adams."


# Conclusion

- Both VMs were built successfully and are fully functional
- Server 19 was renamed to "Houtech" and is ready to be promoted to a domain controller
- The Windows 11 client reached a working desktop and is ready to be joined to the Houtech domain
- This build establishes the environment used across every subsequent project in this portfolio

# networkwalks-week1_extra-project
Android


<div align="center">

# 🔐 Android_setup_in_VirtualBox

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Cybersecurity-404040?style=flat-square&labelColor=C0000" />
  <img src="https://img.shields.io/badge/Virtualbox%20v7.2-0070C0?style=flat-square&labelColor=000000" />
  <img src="https://img.shields.io/badge/Kali%20Linux-v2026.2-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/ANDROID-x86_LAB-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-C00000?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-404040?style=flat-square&labelColor=0070C0&logo=github&logoColor=white" />
  <img src="https://img.shields.io/badge/extra%20project-404040?style=flat-square&labelColor=C00000&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/NetworkWalks-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/Ethical%20Hacking-E87500?style=flat-square&labelColor=000000&logo=kalilinux&logoColor=white" />
 
</p>

---

|  Setting          | Value              |
| ---------------   | ------------------ |
|  Program          | Extra-Networkwalks |
|  Android 9.0 IP   | 10.0.0.9 / 24      |
| Gateway           | 10.0.0.1           |
| DNS               | 8.8.8.8            |






# Step_1: Download the Android-x86 9.0 ISO 
• Open the official Android-x86 download page. 
• Select the Release 9.0 folder link, which leads to the project's official SourceForge 
release page. 
• Choose android-x86_64-9.0-r2.iso for a 64-bit VM, or android-x86-9.0-r2.iso for a 32-bit 
VM. 
• Wait for the download to complete and note where the ISO is saved. 

Link:  Official Android-x86 download page : https://www.android-x86.org/download 

Link:  Android-x86 9.0 release files (SourceForge) : https://sourceforge.net/projects/android-x86/files/Release%209.0/
Tip: Always download from the official android-x86.org page or its linked SourceForge release 
folder. Avoid third-party mirror sites for security reasons. 

# Step_2: Create a new VM in VirtualBox 
• Open VirtualBox, click New 
• Name it Android9-Lab 
• Type: Linux, Version: Other Linux (64-bit) — VirtualBox has no dedicated Android type 
since Android-x86 is Linux-based 
• Memory: 2048 MB (2 GB) is a safe amount 
• Create a virtual hard disk now, VDI format, dynamically allocated, at least 10 GB

# Step_3: Attach the ISO and start install 
• Go to Settings > Storage 
• Click the empty disk icon under Controller 
• Choose the Android-x86 9.0 ISO you downloaded 
• Go to Settings > Display, set Video Memory to at least 64 MB, and enable 3D 
Acceleration 
• Start the VM — the Android-x86 boot menu will appear 
• Choose Installation - Install Android-x86 to harddisk 
• Create/modify partitions, select the virtual disk, choose ext4 filesystem, confirm 
• Choose to install GRUB and make the system writable (yes to both) 
• Let it install, then reboot when prompted 

# Step_4: Set the network to NAT Network 
• Shut down the VM if it booted into Android 
• Go to Settings > Network 
• Attached to: NAT Network 
• Name: pick the same NAT Network your Kali VM uses 
• Start the VM again 

# Step_5: Set a static IP inside Android 
• On the Android home screen, open Settings > Network & Internet > Ethernet (menu 
path may vary slightly by build) 
• Turn off DHCP / switch to Static IP 
• Enter the following: 
◦ IP address: 10.0.0.9 
◦ Subnet mask: 255.255.255.0 
◦ Gateway: 10.0.0.1 
◦ DNS 1: 8.8.8.8

# Step_6: Test connectivity 
• Open the built-in Terminal app on Android (install a terminal emulator APK if not 
present) 
• Run: ping 10.0.0.2 (this should reach your Kali VM) 
• Run: ping 8.8.8.8 (this should confirm internet access) 
• On Kali, run: ping 10.0.0.9 (this should reach Android)



---
author: xkat3r
title: xpimpmykali
date: 2025-02-22
description: How to set up your Kali VM for OSCP
tags: ["OSCP", "OSCP+", "xpimpmykali"]
ShowPostNavLinks: true
ShowBreadCrumbs: true
---

I passed the OSCP and OSCP+ in late 2024 so to give back to the community, I made a tool to set up Kali VM with the essential tools needed for OSCP.

During my preparation for the exam, I spent a lot of time figuring out which tools and versions to use which was frustrating and wasted valuable lab time. For example, I had issues with the latest version of SharpHound and BloodHound. So I had to downgrade and use the earlier versions to resolve incompatibility issues.

Also, there were so many potatoes to use for Windows SeImpersonate privilege. But I relied on only 3 potatoes for the win: GodPotato, PrintSpoofer and JuicyPotato-ng.

The versions and tools in [xpimpmykali](https://github.com/xkat3rZ/xpimpmykali) have been tried and tested on Kali Linux VMware 2024-4. I used these exact tools for my exam as well.

To run this tool, follow the steps below:
1. Take a snapshot of the VM in case the installation doesn't go well
2. `git clone https://github.com/xkat3rZ/xpimpmykali.git`
3. `cd  xpimpmykali`
4. `sudo ./pimpmykali.sh`
5. Enter option menu 'S', enter 'Y' to confirm
6. Wait for about 5-10 mins for the installation to complete
7. Check that the tools are installed in the `/opt` directory
---
title: 'Create shared folder in VMWare Workstation'
date: 2025-04-22
author: 'xkat3r'
description: 'How to set up shared folder in VMWare Workstation Pro'
tags: ["vmware"]
ShowPostNavLinks: true
ShowBreadCrumbs: true
draft: false
---

This guide will help you set up shared folders in VMWare Workstation Pro for UNIX guest VMs such as Kali Linux or Ubuntu.

There are 2 main steps to set up shared folders:
1. In VMWare settings, create a shared folder
   1. In the host machine, edit "Settings" of the VM -> go to "Options" tab -> go to "Shared Folders" row -> Add a new shared folder
   2. In the guest VM, create a folder. This folder will contain the shared folder from the host machine
2. In your guest VM, set up a shared folder
   1. Temporary shared folder
      1. Use `vmhgfs-fuse` command
	     - `sudo vmhgfs-fuse .host:/ <shared_folder_name> -o allow_other -o uid=1000`
	  2. OR
	  3. Use `mount` command
	      - `sudo mount -t fuse.vmhgfs-fuse .host:/ /mnt/hgfs -o allow_other`
   2. Permanent shared folder
      1. `vim /etc/fstab`
		  - Add this line: `.host:/ /mnt/hgfs fuse.vmhgfs-fuse allow_other 0 0`
	  2. Reload entry
		  - `sudo systemctl daemon-reload`
		  - `sudo systemctl restart local-fs.target`
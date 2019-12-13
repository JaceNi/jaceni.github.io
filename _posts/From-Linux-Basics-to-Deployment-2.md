---
layout:     post
title:      From Linux Basics to Deployment 2
subtitle:   Introduction to Permission/User/Group, Mosted Used Software
date:       2018-01-017
author:     Yuchen Ni
header-img: img/post-bg-rwd.jpg
catalog: true
tags:
    - Linux
    - Yuchen Ni
---

After the first post of **From Linux Basics to Deployment 1**, we will discuss Permission/User/Group and Mosted Used Software, in three sections.


## Outline:
- Linux Introduction
- Install Linux
- Permission/User/Group
- Mosted Used Software
- Common Commands/Document Editing
- Shell Script
- Install Software Under Linux
- Project Deployment


## Permission/User/Group(PUG)
1. File Permissions Concept
2. Directory Configuration
3. Directory and Path Operations 
4. Files and Directories Management
5. Files and Content Access
6. Default permissions and Hidden Permissions of Files and Content


- File Permissions Concept:
Linux System has User1 with the files which can be edited by other users ouside the system, and those users can be maanged into diffrent groups.


- Command to check files
1. `ls`:     brief view
2. `ls -l` or `ll`:  view in detals
3. `ls -lh`: view in details of file size
4. `ls -ld`: ciew info of directory
5. `tree`:   in in tree structure
6. `su`: change to root user
7. `su username`: change user with user name of username
8. `su - root`: change to home directory shown as `[root@name ~]# `
9. `pwd`: show the current directory
10. `adduser user1`: add another user user1
11. `passwd user1`: change or create password for user1
12. `cd ..`: enter the previous directory
13. `touch myfile`: create a file (linux does not care about the suffix)
14. `fedit myfile.text`: 


- File Type: 
1. `-`: normal file
2. `d`: folder
3. `b`: block device file (Disk device etc)
4. `|`: link file (shortcut)
5. `c`: serial port device (mouse and keyboard etc)


- File Permissions:
1. `r`: readable
2. `w`: writable
3. `x`: executable
4. `chmod`: modify the file permission
5. `u`: user
6. `g`: same group
7. `o`: other users
8. `a`: all
9. `+`: add permissions
10. `-`: remove permissions
11. `chmod o+w myfile`: add writable permission to other users


- Modify users and groups:
1. `chown -R USER FOLDER_OR_FILE`: modify user
2. `chgrp -R GROUP FILE_OR_FOLDER`: modify group
3. `chown -R USER GROUP FILE_OR_FOLDER`: modify user and folder
4. `chown root myfile`: change owner from user1 to root
5. `chown user1:user1 myfile`: change owner of myfile to user of user1 and group of user1
6. `mkdir FOLDER_NAME`: create a folder (if folders and files are created by root, and the owner of user and the group will be **root user** and **root group** )
7. `chown user1:user1 folder1`: change the folder1 owner and group to **user1** and **user1 group** (but the onwe and group of the files inside the **folder1** will **NOT be changed**)
8. `-R`: recursion of change (change every files and folders inside the target folder)
9. `chown -R user1.user1 folder1`: change the folder1 onwer and group and its every files and folders inside folder1 to user1.


- Directory Configuration:
1. `bin`: executable command file
2. `boot`: startup file
3. `dev`: device file
4. `etc`: confihuration file
5. `home`: user directory
6. `lib`: library file
7. `media`: device mount point file (U disk)
8. `mnt`: manual device mount point
9. `opt`: large software installation package (source code installation package)
10. `usr`: software installation package (similar to windows program files)
11. `prioc`: process file
12. `sbin`: system administrator command file
13. `tmp`: temporary files
14. `var`: log, caching, data files (support large files)
15. `root`: root user (other users will be located into home directory)
**Note: Every Linux Distribution all follows FHS standard, all files are nearly the same.**


- check system information:
1. `uname`: check system name
2. `uname -i`: check system configuration information
3. `uname -r`: check system kernel information
4. `uname -a`: check system all information
5. `lsb_release -a`: check system info
6. `cat /etc/redhat-release`: check system information
7. `dir FOLDER`: check info


- Files and Directories Management
1. `pwd`: show current working directory
2. `cd DIRECTORY`: enter a directory
3. `cd` or `cd ~`: enter /root directory, if user is a noraml user then enter /home/user/
4. `mkdir`: create a directory 
   - (add `-p` can add sub-directories `mkdir -p folder4/subd1/subsubd1`)
   - (`mkdir folder1 folder2 folder3` create multiple folders)
   - (`mkdir folder1/subd1` create a sub-folder)
   - (`mkdir -p folder1/{sub1,sub2,sub3}` create mutiple sub-forlders)
5. `rmdir`: delete empty directory (can add `-p` option)
6.`rm -rf DIRECTORY`: delete folders with files inside (**Dangerous!!! Can Delete Nearly Every Files**)
   - `rm -rf *`: delete everything inside the current rediectory
7. `touch`: create an empty or update a folder visit time
8. `file`: check folder type
9. `cat`: show folder centent (can add `more` or `less` command
10. `/`: absolute path from root/dir1/dir2
11. relative path:
   - `.`:  current directory
   - `..`:  previous directory
   - `-`: switch between two directories
   - `~`: home directory of the user
   - `~user`: enter certain user home directory
12. `echo $PATH`: check PATH info
13. `PATH="..."`: modify PATH


- view file content:
1. `car`: view all the content from first line
2. `tac`: view all the content from last line
3. `nl` or `cat -n`: view with line number
4. `more`: view content with page style
5. `less`: similar with `more`, but it can go back to the previous pages
6. `head`: view first few lines
7. `tail`: view last few lines
    - `tail -n FILE`: only read the last n lines of content
    - 'tail -f FILE': still watching the file updated once changed
8. `od`: view with binary style
9. `q`: quite the content read mode


- file default umask:
1. default permission of file creation (666);   default permission of folder creation (666)
2. umask: 
3. `umask -S`: show current file permission of creation


- file hidden permission:
1. `chattr [+-] [attr] FILE_OR_FOLDER`: modify hidden permission


- view file type:
1. `file /bin/touch`
2. `file /usr/bin/passwd`
3. `file /var/lib/mlocate/mlocate.db`














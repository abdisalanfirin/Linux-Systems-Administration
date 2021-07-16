# Linux Systems Administration

## Ensure/Double Check Permissions on Sensitive Files

Permissions on /etc/shadow should allow only root read and write access.

Command to inspect permissions:  
ls -l

- ![command inspect screenshot](./homework4/snap_1.PNG)

Command to set permissions (if needed): 
sudo chmod <the file>

- ![command permissions screenshot](./homework4/snap_2.PNG)

Permissions on /etc/gshadow should allow only root read and write access. 
sudo chmod 700 /etc/gshadow
Command to inspect permissions: ls -l /etc/gshadow
Command to set permissions (if needed): sudo chmod 700 /etc/gshadow
Permissions on /etc/group should allow root read and write access, and allow everyone else read access only.
sudo chmod 744 /etc/group
Command to inspect permissions: ls -l /etc/group
Command to set permissions (if needed): sudo chmod 744 /etc/group
Permissions on /etc/passwd should allow root read and write access, and allow everyone else read access only.
sudo chmod 744 /etc/passwd
Command to inspect permissions: ls -l /etc/passwd
Command to set permissions (if needed): sudo chmod 744 /etc/passwd

- ![all the users inspect and permissions screenshot](./homework4/snap_3.PNG)

### Step 2: Create User Accounts

Add user accounts for sam, joe, amy, sara, and admin.

sudo adduser.

Command to add each user account (include all five users).

sudo adduser sam 
sudo adduser joe 
sudo adduser amy 
sudo adduser sara 
sudo adduser admin

- ![adding users screenshot](./homework4/snap_4.PNG)

- ![making sure i created all users screenshot](./homework4/snap_x.PNG)

Ensure that only the admin has general sudo access.
sudo -lU admin

- ![only addmin has sudo access screenshot](./homework4/snap_5.PNG)

Command to add admin to the sudo group: sudo usermod -aG admin

- ![adding admin to sudo group](./homework4/snap_6.PNG)

### Step 3: Create User Group and Collaborative Folder

Add an engineers group to the system.

Command to add group: 

sudo addgroup engineers

- ![creating and adding group screenshot](./homework4/snap_7.PNG)

Add users sam, joe, amy, and sara to the managed group.
Command to add users to engineers group (include all four users):
sudo usermod -aG sam
sudo usermod -aG joe
sudo usermod -aG amy
sudo usermod -aG sara
sudo usermod _aG admin

- ![adding users to a group screenshot](./homework4/snap_8.PNG)

Create a shared folder for this group at /home/engineers.
Command to create the shared folder:
sudo mkdir group_sharefolder -p /home/engineer

- ![making a sharefolder for my users screenshot](./homework4/snap_9.PNG)

Change ownership on the new engineers' shared folder to the engineers group.
Command to change ownership of engineer's shared folder to engineer group:

sudo chgrp engineers groups_sharefolder

- ![changing ownership command screenshot](./homework4/snap_10.PNG)

### Step 4: Lynis Auditing

Command to install Lynis: 
sudo apt install lynis

- ![installing lynis screenshot](./homework4/snap_11.PNG)

Command to see documentation and instructions: 
man lynis

- ![lynis documentation and instructions screenshot](./homework4/snap_12.PNG)

Command to run an audit: 
sudo lynis audit system

- ![lynis running audit screenshot](./homework4/snap_13.PNG)

Provide a report from the Lynis output on what can be done to harden the system.

Screenshot of report output:

- ![lynis output report screenshot](./homework4/snap_14.PNG)

### Bonus

Command to install chkrootkit:
sudo apt-get chkrootkit

- ![installing chkrootkit screenshot](./homework4/snap_15.PNG)

Command to see documentation and instructions: man chkrootkit
Command to run expert mode: sudo chkrootkit -x

- ![chkrootkit documentation and instructions screenshot](./homework4/snap_16.PNG)

Provide a report from the chrootkit output on what can be done to harden the system.

Screenshot of end of sample output:

- ![output of chkrootkit screenshot](./homework4/snap_17.PNG)

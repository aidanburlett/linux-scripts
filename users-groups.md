What Users and Groups Are
Linux is a multi‑user operating system, meaning multiple people (or system processes) can use the machine at the same time.
To manage permissions safely, Linux organizes access using:

Users — individual accounts

Groups — collections of users

Permissions — rules that control what users and groups can do

This system keeps files secure and prevents unauthorized access.

Types of Users
1. Root User
The superuser

Has unlimited access

Can modify anything on the system

Use with caution

2. Regular Users
Normal accounts

Limited permissions

Can only access their own files unless given permission

3. System Users
Created by the OS

Run background services (e.g., www-data, daemon)

Not used for login

What Groups Are
A group is a collection of users that share permissions.

Examples:

sudo → users allowed to run admin commands

www-data → web server processes

adm → users who can read system logs

Groups make permission management easier.

Viewing Users and Groups
View current user
Code
whoami
View all users
Code
cat /etc/passwd
View all groups
Code
cat /etc/group
View your groups
Code
groups
Creating and Managing Users
Create a new user
Code
sudo adduser username
Delete a user
Code
sudo deluser username
Change a user’s password
Code
sudo passwd username
Creating and Managing Groups
Create a group
Code
sudo groupadd groupname
Delete a group
Code
sudo groupdel groupname
Add a user to a group
Code
sudo usermod -aG groupname username
Remove a user from a group
Code
sudo gpasswd -d username groupname
Primary vs Secondary Groups
Primary Group
Assigned when the user is created

Usually the same name as the user

Owns files the user creates

Secondary Groups
Additional groups the user belongs to

Provide extra permissions

Example:
A user might be in:

primary group: aidan

secondary groups: sudo, adm, docker

Checking User Details
View user info
Code
id username
Example output:

Code
uid=1000(aidan) gid=1000(aidan) groups=1000(aidan),27(sudo)
Breakdown:

uid → user ID

gid → primary group ID

groups → all groups the user belongs to

Why Users & Groups Matter
Understanding users and groups helps you:

Manage permissions

Secure your system

Control access to files

Run services safely

Prepare for cybersecurity work

This is foundational Linux knowledge — and you’re building it the right way.

Practice Commands
Try these inside your Linux/practice/ folder:

Check your user  
whoami

List your groups  
groups

Create a test user  
sudo adduser testuser

Add test user to sudo  
sudo usermod -aG sudo testuser

View user details  
id testuser
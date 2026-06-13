What Linux Permissions Are
Linux permissions control who can read, write, or execute a file or directory. Every file has three permission groups:

Owner — the user who owns the file

Group — users in the same group

Others — everyone else on the system

Each group can have three types of permissions:

Read (r) — view file contents or list directory

Write (w) — modify file or directory

Execute (x) — run file or enter directory

How to View Permissions
Use:

Code
ls -l
You’ll see something like:

Code
-rwxr-xr--
Breakdown:

First character: file type (- = file, d = directory)

Next 3: owner permissions

Next 3: group permissions

Last 3: others permissions

Changing Permissions with chmod
Symbolic method
Code
chmod u+x file.sh
u = user (owner)

g = group

o = others

a = all

Examples:

Add execute for owner:
chmod u+x script.sh

Remove write for group:
chmod g-w notes.txt

Give everyone read:
chmod a+r file.txt

Numeric (octal) method
Each permission has a number:

read = 4

write = 2

execute = 1

Add them together:

7 = rwx

6 = rw-

5 = r-x

4 = r--

Example:

Code
chmod 755 script.sh
Means:

owner: 7 (rwx)

group: 5 (r-x)

others: 5 (r-x)

Changing Ownership
Change owner
Code
sudo chown username file.txt
Change owner and group
Code
sudo chown username:group file.txt
Directory Permissions
For directories:

read (r) → list files

write (w) → create/delete files

execute (x) → enter the directory

Example:

Code
chmod 755 myfolder
Common Permission Setups
Scripts you want to run:
chmod 755 script.sh

Private files:
chmod 600 secrets.txt

Shared directories:
chmod 770 shared/

Practice Commands
Try these inside your Linux/practice/ folder:

View permissions  
ls -l

Add execute permission  
chmod u+x test.sh

Remove write permission  
chmod g-w file.txt

Set numeric permissions  
chmod 644 notes.md
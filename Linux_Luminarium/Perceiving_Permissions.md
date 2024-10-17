# Perceiving Permissions
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Changing File Ownership
**Commands used:**
- `chown [username] [file]`  : Used to change the ownership of files
- `ls -l`  : Used to view all the files/directories and what users have what permissions over them, while viewing some things to keep in mind are, if it starts with "-" its a file and if it starts "d" its a directory, the next nine characters are the actual access permissions of the file or directory, split into 3 characters denoting the permissions that the user who owns the file (termed the "owner") has to the file, 3 characters denoting the permissions that the group that owns the file (termed the "group") has to the file, and 3 characters denoting the permissions that all other access (e.g., by other users and other groups) has to the file, in these characters `r` denotes the permission to read, `w` denotes the permission to write, `x` denotes permission to execute. There are also two columns showing the user that owns the file and then the group that owns the file.

**Thought Process:**
- We first find the permissions given to the `/flag` file, we find its only allowed to be accessed by "root" user so we need to change the owner of the `/flag` file to the "hacker" user to gain access to it so that we can read the file to get the flag thus we do that by using the `chown` command.

**Solution:**
- Start the challenge, go to `/` directory by entering `cd /` and input the command `ls -l` to view the permissions of "/flag" file, we see that only "root" is allowed to access it, so change its permissions to allow "hacker" i.e us to gain access, we do that by using the command `chown hacker flag` to give us permissions then we read the file using `cat flag` to get the flag.

**Flag Obtained:**
> *pwn.college{8wUSQn28ENp6U0zvnjHBUaQbcLg.dFTM2QDLwMTN0czW}*

## Groups and Files
**Commands used:**
- `id`    : Used to check what groups you are part of
- `chgrp` : Used to change the group ownership of files

**Thought Process:**
- We first find the permissions given to the `/flag` file, we find its only allowed to be accessed by "root" group so we need to change the group ownership of the `/flag` file to the "hacker" group to gain access to it so that we can read the file to get the flag thus we do that by using the `chgrp` command.

**Solution:**
- Start the challenge, go to `/` directory by entering `cd /` and input the command `ls -l` to view the permissions of "/flag" file, we see that only "root" group is allowed to access it, so change its permissions to allow "hacker" group i.e us to gain access, we do that by using the command `chgrp hacker flag` to give us permissions then we read the file using `cat flag` to get the flag.

**Flag Obtained:**
> *pwn.college{wLgEbFY71AS1CM-nsk9WIxLwv81.dFzNyUDLwMTN0czW}*

## Funs With Groups Names
**Commands used:**
- `c`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## Changing Permissions
**Commands used:**
- `c`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## Executable Files
**Commands used:**
- `c`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## Permission Tweaking Practice
**Commands used:**
- `c`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## Permissions Setting Practice
**Commands used:**
- `c`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## The SUID Bit
**Commands used:**
- `c`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

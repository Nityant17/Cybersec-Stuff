# Perceiving Permissions
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Changing File Ownership
**Commands used:**
- `chown [username] [file]`  : Used to change the ownership of files
- `ls -l`  : Used to view all the files/directories and what users have what permissions over them, while viewing some things to keep in mind are, if it starts with "-" its a file and if it starts "d" its a directory, the next nine characters are the actual access permissions of the file or directory, split into 3 characters denoting the permissions that the user who owns the file (termed the "owner") has to the file, 3 characters denoting the permissions that the group that owns the file (termed the "group") has to the file, and 3 characters denoting the permissions that all other access (e.g., by other users and other groups) has to the file, in these characters `r` denotes the permission to read, `w` denotes the permission to write, `x` denotes permission to execute. There are also two columns showing the user that owns the file and then the group that owns the file.

**Thought Process:**
- We first find the ownerships of the `/flag` file, we find its only allowed to be accessed by "root" user so we need to change the owner of the file to the "hacker" user to gain access to it so that we can read the file to get the flag thus we do that by using the `chown` command.

**Solution:**
- Start the challenge, go to `/` directory by entering `cd /` and input the command `ls -l` to view the owners of "/flag" file, we see that only "root" is allowed to access it, so change its ownerships to allow "hacker" i.e us to gain access, we do that by using the command `chown hacker flag` to give us the ownership then we read the file using `cat flag` to get the flag.

**Flag Obtained:**
> *pwn.college{8wUSQn28ENp6U0zvnjHBUaQbcLg.dFTM2QDLwMTN0czW}*

## Groups and Files
**Commands used:**
- `id`    : Used to check what groups you are part of
- `chgrp` : Used to change the group ownership of files

**Thought Process:**
- We first find the ownerships of the `/flag` file, we find its only allowed to be accessed by "root" group so we need to change the group ownership of the file to the "hacker" group to gain access to it so that we can read the file to get the flag thus we do that by using the `chgrp` command.

**Solution:**
- Start the challenge, go to `/` directory by entering `cd /` and input the command `ls -l` to view the owners of "/flag" file, we see that only "root" group is allowed to access it, so change its ownership to allow "hacker" group i.e us to gain access, we do that by using the command `chgrp hacker flag` to give us the ownership then we read the file using `cat flag` to get the flag.

**Flag Obtained:**
> *pwn.college{wLgEbFY71AS1CM-nsk9WIxLwv81.dFzNyUDLwMTN0czW}*

## Funs With Groups Names
**Commands used:**
- `id`    : Used to check what groups you are part of
- `chgrp` : Used to change the group ownership of files

**Thought Process:**
- We first find the ownerships of the `/flag` file, we find its only allowed to be accessed by "root" group so we need to change the group ownership of the file to the our group to gain access to it so that we can read the file to get the flag thus we do that by using the `chgrp` command but we dont know what group we are in so find that using `id` command. 

**Solution:**
- Start the challenge, go to `/` directory by entering `cd /` and input the command `ls -l` to view the owners of "/flag" file, we see that only "root" group is allowed to access it, so change its ownerships to allow our group to gain access, but first we need to find our group name by entering `id`, we find that our group name is "grp4665", now change the ownership by using the command `chgrp grp4665 flag` to give us access then we read the file using `cat flag` to get the flag.

**Flag Obtained:**
> *pwn.college{kyf-66T_Fh05qpf-Mq0C2_TAucP.dJzNyUDLwMTN0czW}*

## Changing Permissions
**Commands used:**
- `chmod [OPTIONS] MODE FILE`  : Used to change the permissions of files, it uses the format of "WHO+/-WHAT" where "WHO" is user(u), group(g), other(o) or all(a) and "WHAT" is read(r), write(w) or execute(x) and "+" is used to add permission while "-" is used to revoke permissions 

**Thought Process:**
- We first find the permissions of the `/flag` file, we find its only allowed to be read by "root" user so we need to change the permissions of the `/flag` file to be able to read it so we do that by using `chmod` command.

**Solution:**
- Start the challenge, input the command `cd /` to go to `/` directory and use `ls -l` see the permissions given to "/flag" file, we see only "root" user is allowed to read it so we modify its permissions to give us access to read it by adding the permission to read to all users using the command `chmod a+r flag` then we use the command `cat flag` to read the file and get the flag.

**Flag Obtained:**
> *pwn.college{s9bA-Muaws5tr_Z1iJ-bZcVboif.dNzNyUDLwMTN0czW}*

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

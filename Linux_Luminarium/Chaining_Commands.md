# Chaining Commands
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Chaining with Semicolons
**Commands used:**
- `;`  : Used to to chain commands

**Thought Process:**
- Need to run `/challenge/pwn` and then `/challenge/college`, chaining them with a semicolon to get the flag.

**Solution:**
- Start the challenge, input the command `/challenge/pwn;/challenge/college` to chain them and get the flag.  

**Flag Obtained:**
> *pwn.college{MgS5isnKKLvyTnaIqVc5-6xlhpU.dVTN4QDLwMTN0czW}*

## Your First Shell Script
**Commands used:**
- `bash file.sh`  : Used to execute shell scripts i.e a ".sh" file containing commands to be run also all of the various redirection methods work: `>` for stdout, `2>` for stderr, `<` for stdin, `>>` and `2>>` for append-mode redirection, `>&` for redirecting to other file descriptors, and `|` for piping to another command 

**Thought Process:**
- Need to run `/challenge/pwn` and then `/challenge/college`, but this time in a shell script called "x.sh", then run it with `bash` to get the flag.

**Solution:**
- Start the challenge, input the command `vim x.sh` to create the script and open it in vim editor and write the commands `/challenge/pwn` and then `/challenge/college` in it, then execute this script by entering `bash x.sh` to get the flag.   

**Flag Obtained:**
> *pwn.college{0i6rUO31jprdk_WjcmvswMBD9jx.dFzN4QDLwMTN0czW}*

## Redirecting Script Output
**Commands used:**
- `bash file.sh`  : Used to execute shell scripts i.e a ".sh" file containing commands to be run also all of the various redirection methods work: `>` for stdout, `2>` for stderr, `<` for stdin, `>>` and `2>>` for append-mode redirection, `>&` for redirecting to other file descriptors, and `|` for piping to another command  

**Thought Process:**
- Need to create a script that calls the `/challenge/pwn` command followed by the `/challenge/college` command, and pipe the output of the script into a single invocation of the `/challenge/solve` command to get the flag.

**Solution:**
- Start the challenge, input the command `vim x.sh` to create the script and open it in vim editor and write the commands `/challenge/pwn` and then `/challenge/college` in it, then execute this script and pipe its output to `/challenge/solve` by entering `bash x.sh | /challenge/solve` to get the flag. 

**Flag Obtained:**
> *pwn.college{g2ke9pRve_QrUAs4ACv4Id49X67.dhTM5QDLwMTN0czW}*

## Executable Shell Scripts
**Commands used:**
- `su`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
> **

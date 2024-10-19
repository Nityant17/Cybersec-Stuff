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
- `bash file.sh`  : Used to execute shell scripts i.e a ".sh" file containing commands to be run 

**Thought Process:**
- Need to run `/challenge/pwn` and then `/challenge/college`, but this time in a shell script called "x.sh", then run it with `bash` to get the flag.

**Solution:**
- Start the challenge, input the command `vim x.sh` to create the script and open it in vim editor and write the commands `/challenge/pwn` and then `/challenge/college` in it, then execute this script by entering `bash x.sh` to get the flag.   

**Flag Obtained:**
> *pwn.college{0i6rUO31jprdk_WjcmvswMBD9jx.dFzN4QDLwMTN0czW}*

## Redirecting Script Output
**Commands used:**
- `su`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
> **

## Executable Shell Scripts
**Commands used:**
- `su`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
> **

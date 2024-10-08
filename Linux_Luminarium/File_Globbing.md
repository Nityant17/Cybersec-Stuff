# File Globbing
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Matching with *
**Commands used:**
- `*`  : Used to shorten the file path, the shell will treat it as "wildcard" and try to replace that argument with any files that match the pattern

**Thought Process:**
- Need to run the "run" program after entering the "/challenge" directory using `cd` but only passing less than 4 characters, so use `*` to shorten the path and get the flag.

**Solution:**
- Start the challenge, input the command `cd /ch*` to change the directory to "/challenge" while satisfying the conditions and then enter the command `./r*` to run the program and get the flag.

**Flag Obtained:**
> *pwn.college{MlUFtrn5HSlrrx9GLjcFydt_74b.dFjM4QDLwMTN0czW}*

## Matching with ?
**Commands used:**
- `?`  : Used to shorten the file path, the shell will treat it as "single character wildcard" and try to replace that argument with any files that match the pattern  

**Thought Process:**
- Need to run the "run" program after entering the "/challenge" directory using `cd` but not using "c" or "l", so use `?` to replace them with a wild character and get the flag. 

**Solution:**
- Start the challenge, input the command `cd /?ha??enge` to change the directory to "/challenge" while satisfying the conditions and then enter the command `./run` to run the program and get the flag.   

**Flag Obtained:**
> *pwn.college{YIj62iTE7b3mNDBf9Udk-5YC9M-.dJjM4QDLwMTN0czW}*

## Matching with []
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Matching paths with []
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Mixing globs
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Exclusionary globbing
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

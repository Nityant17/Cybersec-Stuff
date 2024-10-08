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
- Need to run the "run" program after entering the "/challenge" directory using `cd` but not using "c" or "l", so use `?` to replace them with a wildcard and get the flag. 

**Solution:**
- Start the challenge, input the command `cd /?ha??enge` to change the directory to "/challenge" while satisfying the conditions and then enter the command `./run` to run the program and get the flag.   

**Flag Obtained:**
> *pwn.college{YIj62iTE7b3mNDBf9Udk-5YC9M-.dJjM4QDLwMTN0czW}*

## Matching with []
**Commands used:**
- `[]`  : Used to shorten the file path, the shell will treat it as a "wildcard for some subset of potential characters", specified within the brackets  

**Thought Process:**
- Need to change your working directory to "/challenge/files" and run `/challenge/run` with a single argument that bracket globs into "file_b", "file_a", "file_s", and "file_h" so use `[]` to create the set of wildcards and satisfy the condition to get the flag.

**Solution:**
- Start the challenge, input the command `cd /challenge/files` to change the directory to "challenge/files" and then use the command `/challenge/run file_[absh]` to the run the program satisfying all the conditions and get the flag. 

**Flag Obtained:**
> *pwn.college{kRXXvhHS4_iitjLUmWWXE0uo_YD.dNjM4QDLwMTN0czW}*

## Matching paths with []
**Commands used:**
- `[]`  : Used to shorten the file path, the shell will treat it as a "wildcard for some subset of potential characters", specified within the brackets  

**Thought Process:**
- Need to run `/challenge/run` from the home directory with a single argument that bracket globs into the absolute paths to the "file_b", "file_a", "file_s, and "file_h" files in the "/challenge/files" directory.

**Solution:**
- Start the challenge, input the command `/challenge/run /challenge/files/file_[absh]` to the run the program satisfying all the conditions and get the flag.   

**Flag Obtained:**
> *pwn.college{4N6OIBlbSePoPzszKVMB22fba6c.dRjM4QDLwMTN0czW}*

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

# Pondering PATH
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## The PATH Variable
**Commands used:**
- `PATH`  : A special shell variable used to store a bunch of directory paths in which the shell will search for programs corresponding to commands called

**Thought Process:**
- Need to disrupt the operation of the `/challenge/run` program which will DELETE the flag file using the `rm` command so to disrupt it we clear the `PATH` variable thus its not able to find the `rm` command and we get the flag.

**Solution:**
- Start the challenge, input the command `PATH=""` to clear the path variable and then run the program `/challenge/run` and since it cant find `rm` we get the flag. 

**Flag Obtained:**
> *pwn.college{wHwgd3LutZFG6zqSe1oSgb_ysqe.dZzNwUDLwMTN0czW}*

## Setting PATH
**Commands used:**
- `c`  : Used to

**Thought Process:**
- Need to run 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
> **

## Adding Commands
**Commands used:**
- `c`  : Used to

**Thought Process:**
- Need to run 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
> **

## Hijacking Commands
**Commands used:**
- `c`  : Used to

**Thought Process:**
- Need to run 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
> **

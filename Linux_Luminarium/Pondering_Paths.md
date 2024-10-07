# Pondering Paths  
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## The Root
**Commands used:**
- `/path/to/program`  : Used to run the program with the given absolute path

**Thought Process:**
- Need to run a program "pwn" so have to provide the path to the program.  

**Solution:**
- Start the challenge, input the command `/pwn` to provide the absolute path to the program "pwn" and run the program to get the flag.  

**Flag Obtained:**
- *pwn.college{wTJXuNWgdAtmNcWldhERWicO1lI.dhzN5QDLwMTN0czW}* 

## Program and absolute paths
**Commands used:**
- `/path/to/program`  : Used to run the program with the given absolute path 

**Thought Process:**
- Need to run a program "run" so have to provide the path to the program.  

**Solution:**
- Start the challenge, input the command `/challenge/run` to provide the absolute path to the program "run" and run the program to get the flag.  

**Flag Obtained:**
- *pwn.college{8q0lSIhwUn4jHnAD_31630V3XBz.dVDN1QDLwMTN0czW}* 

## Position thy self
**Commands used:**
- `cd path`           : Used to change the working directory to the one with the specified path
- `/path/to/program`  : Used to run the program with the given absolute path

**Thought Process:**
- Need to run a program "run" so we provide the path to the program, it shows we need to be in "etc" directory so use `cd path` to go into "etc" and then run the program again.    

**Solution:**
- Start the challenge, use `cd path` command to go into "etc" directory, input `/challenge/run` to provide the absolute path to the program "run" and run the program to get the flag.  

**Flag Obtained:**
- *pwn.college{8VKb_2A6RrzhdOXbDnaJIEYiKKF.dZDN1QDLwMTN0czW}* 

## Position elsewhere
**Commands used:**
- `cd path`           : Used to change the working directory to the one with the specified path
- `/path/to/program`  : Used to run the program with the given absolute path

**Thought Process:**
- Need to run a program "run" so we provide the path to the program, it shows we need to be in "/var/log" directory so use `cd path` to go into "/var/log" and then run the program again.  

**Solution:**
- Start the challenge, use `cd path` command to go into "/var/log" directory, input `/challenge/run` to provide the absolute path to the program "run" and run the program to get the flag.  

**Flag Obtained:**
- *pwn.college{sq5gPhcSYO1IXoVXMgbA5bk37AU.ddDN1QDLwMTN0czW}* 

## Position yet elsewhere
**Commands used:**
- `cd path`           : Used to change the working directory to the one with the specified path
- `/path/to/program`  : Used to run the program with the given absolute path

**Thought Process:**
- Need to run a program "run" so we provide the path to the program, it shows we need to be in "/usr/share/doc/fontconfig" directory so use `cd path` to go into "/usr/share/doc/fontconfig" and then run the program again.  

**Solution:**
- Start the challenge, use `cd path` command to go into "/usr/share/doc/fontconfig" directory, input `/challenge/run` to provide the absolute path to the program "run" and run the program to get the flag.  

**Flag Obtained:**
- *pwn.college{4mJoojKB4Gz206TM6miaVQ72bml.dhDN1QDLwMTN0czW}* 

## Implicit relative paths, from /
**Commands used:**
- `cd path`        : Used to change the working directory to the one with the specified path
- `relative/path`  : Used to run the program with the given relative path

**Thought Process:**
- Need to run a program "run" so we provide the path to the program, it shows we need to provide a relative path from root directory so use `cd path` to go into "/" and then input relative path to run the program again.  

**Solution:**
- Start the challenge, use `cd path` command to go into "/" directory, input `challenge/run` to provide the relative path to the program "run" and run the program to get the flag.  

**Flag Obtained:**
- *pwn.college{cdmWFrVZpnLI6wUe9dYAsKKgZdo.dlDN1QDLwMTN0czW}* 

## Explicit relative paths, from /
**Commands used:**
- `cd path`          : Used to change the working directory to the one with the specified path
- `./relative/path`  : Used to run the program with the given relative path

**Thought Process:**
- Need to run a program "run" so we provide the path to the program, it shows we need to provide a relative path from root directory and must start with "." so use `cd path` to go into "/" and then input relative path starting with `./` to run the program again as "." refers to same directory currently in so it doesnt affect the path.  

**Solution:**
- Start the challenge, use `cd path` command to go into "/" directory, input `./challenge/run` to provide the relative path starting with "." to the program "run" and run the program to get the flag.  

**Flag Obtained:**
- *pwn.college{coz0ZGgYzP4ni0nXG4QNMPBUqY6.dBTN1QDLwMTN0czW}* 

## Implicit relative path
**Commands used:**
- `cd path`          : Used to change the working directory to the one with the specified path
- `./relative/path`  : Used to run the program with the given relative path

**Thought Process:**
- Need to run a program "run" so we provide the path to the program, it shows we need to run the program from "challenge" directory so use `cd path` to go into "/challenge" and then input `./run` to run the program as "." refers to same directory currently in so it doesnt affect the path and without `./` if you enter just the program name it will refer to program name "run" as command and give an error.  

**Solution:**
- Start the challenge, use `cd path` command to go into "/challenge" directory, input `./run` to run the program and get the flag.  

**Flag Obtained:**
- *pwn.college{Idyan8aOFERShuQwk7RGvkrrmFo.dFTN1QDLwMTN0czW}* 

## Home sweet Home
**Commands used:**
- `/path/to/program`  : Used to run the program with the given absolute path

**Thought Process:**
- Need to run a program "run" so we provide the path to the program, it shows we need to provide the destination where the flag will be copied to as an argument, it must be less than 3 characters and the destination must be inside home directory so provide `~/f` as argument, here `~` is used to represent home directory and thus satsify all the conditions to get the flag.  

**Solution:**
- Start the challenge, input `/challenge/run ~/f` to run the program and get the flag.  

**Flag Obtained:**
- *pwn.college{o1FKZ_kQrruvJHIsAgnoa9hoE5a.dNzM4QDLwMTN0czW}* 

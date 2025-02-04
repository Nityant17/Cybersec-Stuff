# Digesting Documentation
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Learning From Documentation
**Commands used:**
- `cmnd -argument`  : Used to run the command with specific arguments 

**Thought Process:**
- Need to run the "challenge" program with the correct argument, so give the command the required argument using `-argument` and get the flag. I got all the information on what we need to do by reading the documentation of this challenge.

**Solution:**
- Start the challenge, read the documentation to understand what we need to do, input the command `/challenge/challenge --giveflag` to run the program with the required argument as per the documentation and get the flag.  

**Flag Obtained:**
> *pwn.college{Q5hStYegQFhFMrZvpYIb5KG3a4R.dRjM5QDLwMTN0czW}*

## Learning Complex Usage
**Commands used:**
- `cmnd -argument subargument`  : Used to run the command with specific arguments

**Thought Process:**
- Read the documentation and found out that we need to run the "challenge" program with the correct argument and also provide the subargument to it, so just add the arguments as needed in the command and run the program to get the flag.

**Solution:**
- Start the challenge, read the documentation to understand what we need to do, first find the file that has the flag using `ls` after finding it was "not-the-flag", input the command `/challenge/challenge --printfile not-the-flag` to run the program with the required argument as per the documentation and get the flag.

**Flag Obtained:**
> *pwn.college{oej8CtxUOOQbGel2VUn4AJKPiu4.dVjM5QDLwMTN0czW}*

## Reading Manuals
**Commands used:**
- `man`  : Used to display (if available) the manual of the command you pass as an argument

**Thought Process:**
- Need to find the secret argument of `challenge` that will give the flag, so find it using `man` command and run the program with the argument to get the flag.

**Solution:**
- Start the challenge, input the command `man challenge` to find all the argument options for the command, we find that if we run the program `/challenge/challenge` with the argument `--batbgf 797` it will give the flag, so use the command `/challenge/challenge --batbgf 797` to get the flag.  

**Flag Obtained:**
> *pwn.college{QbMXa7tbg9fQ7WqN6us4x3onlKI.dRTM4QDLwMTN0czW}*

## Searching Manuals
**Commands used:**
- `man`  : Used to display (if available) the manual of the command you pass as an argument

**Thought Process:**
- Need to find the secret argument of `challenge` that will give the flag, so find it using `man` command and traversing the pages using the movement keys and run the program with the argument to get the flag.

**Solution:**
- Start the challenge, input the command `man challenge` and use `/flag` in the man page as the arguments info must contain the word "flag" in it to find the correct argument, we find that if we run the program `/challenge/challenge` with the argument `--ophdxew` it will give the flag, so use the command `/challenge/challenge --ophdxew` to get the flag.  

**Flag Obtained:**
> *pwn.college{QjFZDIOaU6UBKs7H8xbWI5b_6bz.dVTM4QDLwMTN0czW}*

## Searching For Manuals
**Commands used:**
- `man`  : Used to display (if available) the manual of the command you pass as an argument

**Thought Process:**
-  Need to find the secret argument of `challenge` that will give the flag, so find it using `man` command and run the program with the argument to get the flag but the man page is hidden under a different name so find the correct man page using an argument with `man`, to find the arguments of `man` and what they do view the man page of `man` and use the correct argument to find the man page and thus find the secert argument of `challenge`.

**Solution:**
- Start the challenge, input the command `man man` to view the man page of `man` and find the argument needed, we see that `-k pattern` can be used to find all the man pages with the "pattern" in their description. We know that the secret man page will contain the string "/challenge/challenge" as it will be the man page of `challenge` command, so use `man -k /challenge/challenge` to find the correct man page. We find that the command has been renamed to `gmuphjaydw` so open its man page using `man gmuphjaydw`, here we see that if we run the program with the argument `--gmuphj 801` it will give the flag, so run the command `/challenge/challenge --gmuphj 801` to get the flag.     

**Flag Obtained:**
> *pwn.college{80D_1R9gUHUJV-4muLVp3NhjayL.dZTM4QDLwMTN0czW}* 

## Helpful Programs
**Commands used:**
- `cmnd --help`  : Used to tell how to run the command 

**Thought Process:**
- Need to find the secret argument of `challenge` that will give the flag, so find it using `--help` argument and run the program with the argument to get the flag.

**Solution:**
- Start the challenge, input the command `/challenge/challenge --help` to see how to run the command, we see that if we use the argument `-g value` with the correct value it will give the flag and if we use the argument `-p` it will show what value we need to input. So use the command `/challenge/challenge -p` it shows that the value is "8" so run the command `/challenge/challenge -g 8` to get the flag.

**Flag Obtained:**
> *pwn.college{wY0EjKlUZhe0Sa8DIhr-93ZD4ph.ddjM4QDLwMTN0czW}*

## Help For Builtins
**Commands used:**
- `help cmnd`  : Used to get a list of arguments of shell builtin cmnds

**Thought Process:**
- Need to find the secret argument of `challenge` that will give the flag, so find it using `help cmnd` command as `challenge` is a builtin command here and run the program with the argument to get the flag.

**Solution:**
- Start the challenge, input the command `help challenge` to find the arguments, we find that using the argument `--secret 0FOCCYi0` will give the flag, so use the command `challenge --secret 0FOCCYi0` to get the flag.  

**Flag Obtained:**
> *pwn.college{0FOCCYi0NPOjsvDeThA0zjVWCxJ.dRTM5QDLwMTN0czW}* 


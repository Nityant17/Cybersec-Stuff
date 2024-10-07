# Comprehending Commands  
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## cat: not the pet, but the command!
**Commands used:**
- `cat`  : Used to concatenate/read files

**Thought Process:**
- Need to read the "flag" file to get the flag, so read it using `cat` command.

**Solution:**
- Start the challenge, input the command `cat flag` to read the file "flag" and get the flag. 

**Flag Obtained:**
- *pwn.college{AbnHoFH1cTooNQJfHC_ErzHMwv5.dFzN1QDLwMTN0czW}* 

## catting absolute paths
**Commands used:**
- `cat /path/to/file`  : Used to concatenate/read files with specified absolute path

**Thought Process:**
- Need to read the "flag" file in "/" directory to get the flag, so read it using `cat /path/to/file` command.

**Solution:**
- Start the challenge, input the command `cat /flag` to read the file "flag" specified by its absolute path and get the flag.  

**Flag Obtained:**
- *pwn.college{0RpfeW_1ktmqLLoVtFJRvh9VZDA.dlTM5QDLwMTN0czW}* 

## more catting practice
**Commands used:**
- `cat /path/to/file`  : Used to concatenate/read files with specified absolute path 

**Thought Process:**
- Need to read the "flag" file in "/usr/aarch64-linux-gnu/" directory without using cd to get the flag i.e open with absolute path, so read it using `cat /path/to/file` command. 

**Solution:**
- Start the challenge, input the command ` cat /usr/aarch64-linux-gnu/flag` to read the file "flag" specified by its absolute path and get the flag.     

**Flag Obtained:**
- *pwn.college{oBrZuXVh0wVu5jxaRpRcziMAOmZ.dBjM5QDLwMTN0czW}* 

## grepping for a needle in a haystack
**Commands used:**
- `grep SEARCH_STRING /path/to/file`  : Used to search for a particular string in files

**Thought Process:**
- Need to search for the flag in `/challenge/data.txt` a file with alot of data, so use `grep` to search for the line with string "pwn.college" since all flags start with that and that will be the flag.

**Solution:**
- Start the challenge, input the command `grep "pwn.college" /challenge/data.txt` to get the line which conatins "pwn.college" in the file and get the flag.

**Flag Obtained:**
- *pwn.college{wQ5TQZyp-llG-pp5lTsA4U8XP6M.ddTM4QDLwMTN0czW}* 

## listing files
**Commands used:**
- `ls /path`  : Used to list files in all the directories provided to it as path, and in the current directory if no path is provided

**Thought Process:**
- Need to find the new name of "/run" file to run the program, so use the `ls` command to see all the files inside of "/challenge" and find the new program file to run and get the flag. 

**Solution:**
- Start the challenge, input the command `ls /challenge/` to view all the files inside "/challenge" directory and find the one to run, the file was renamed to "25245-renamed-run-19645" now run the command `/challenge/25245-renamed-run-19645` to run the program and get the flag. 

**Flag Obtained:**
- *pwn.college{ELSh0QSexQTjRsdr1FUw9r5OZhl.dhjM4QDLwMTN0czW}* 

## touching files
**Commands used:**
- `touch`  : Used to create a new blank file

**Thought Process:**
- Need to create 2 new file `/tmp/pwn` and `/tmp/college` to be able to run the "/run" file, so create them by using `touch` command and providing the path and name of these files as argument, then run the "/run" file to get the flag.

**Solution:**
- Start the challenge, input the command `touch /tmp/pwn` and `touch /tmp/college` to create the files, now run the "/run" file using `/challenge/run` to get the flag. 

**Flag Obtained:**
- *pwn.college{QXfoEI3dO67N5wDy5N_nwNm4f1T.dBzM4QDLwMTN0czW}* 

## removing files
**Commands used:**
- `cat`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
- ** 

## hidden files
**Commands used:**
- `cat`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
- ** 

## An Epic Filesystem Quest
**Commands used:**
- `cat`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
- ** 

## making directories
**Commands used:**
- `cat`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
- ** 

## finding files
**Commands used:**
- `cat`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
- ** 

## linking files
**Commands used:**
- `cat`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command  

**Flag Obtained:**
- ** 

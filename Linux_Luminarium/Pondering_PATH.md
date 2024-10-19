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
- `PATH`  : A special shell variable used to store a bunch of directory paths in which the shell will search for programs corresponding to commands called

**Thought Process:**
- Need to run `/challenge/run` which will run the `win` command via its bare name, but this command exists in the `/challenge/more_commands/` directory, which is not initially in the `PATH` so we can just overwrite `PATH` with this directory so the shell knows where to find the command and can run with its bare name. 

**Solution:**
- Start the challenge, input the command `PATH="/challenge/more_commands/"` to overwrite the variable to allow the shell to find `win` command, now run the program `/challenge/run` and get the flag.   

**Flag Obtained:**
> *pwn.college{8XQ9rf6ZrePKQpAQlRu2tbDmPiH.dVzNyUDLwMTN0czW}*

## Adding Commands
**Commands used:**
- `PATH`  : A special shell variable used to store a bunch of directory paths in which the shell will search for programs corresponding to commands called
- `bash file.sh`  : Used to execute shell scripts i.e a ".sh" file containing commands to be run also all of the various redirection methods work: `>` for stdout, `2>` for stderr, `<` for stdin, `>>` and `2>>` for append-mode redirection, `>&` for redirecting to other file descriptors, and `|` for piping to another command

**Thought Process:**
- Need to run `/challenge/run` which will run the `win` command via its bare name, but this command doesnt exist so we need to make a shell script named `win` which will read the `/flag` file to get the flag, and add its directory to `PATH` so the shell knows where to find the command and can run with its bare name. While modifying `PATH` we need to make sure the shell can still find the path to the command used in the `win` script to use it.

**Solution:**
- Start the challenge, input the command `vim win` to create the script and open it in vim editor and write the command `cat /flag` in it, then also make it executable by using `chmod u+x win` then we need to add it to the `PATH` but we need to be careful while changing `PATH` so we just check what `PATH` contains using `echo $PATH` and also copy it while modifiying `PATH` so the final command we enter to modify `PATH` is `PATH="/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/hacker"` to add the directory that `win` is in so that it can be ran. Now finally we run `/challenge/run` and get the flag.   

**Flag Obtained:**
> *pwn.college{AfBA422ZX_LRcroZwQI8gopm5ay.dZzNyUDLwMTN0czW}*

## Hijacking Commands
**Commands used:**
- `PATH`  : A special shell variable used to store a bunch of directory paths in which the shell will search for programs corresponding to commands called
- `bash file.sh`  : Used to execute shell scripts i.e a ".sh" file containing commands to be run also all of the various redirection methods work: `>` for stdout, `2>` for stderr, `<` for stdin, `>>` and `2>>` for append-mode redirection, `>&` for redirecting to other file descriptors, and `|` for piping to another command

**Thought Process:**
- Need to run `/challenge/run` which will run the `rm` command which will delete the flag, so what we do to avoid this is create a new script `rm` and modify the `PATH` variable to direct the shell to the new `rm` command which will read the flag instead of the one that will delete it. While modifying `PATH` we need to make sure the shell can still find the path to the command used in the new `rm` script to use it.

**Solution:**
- Start the challenge, input the command `vim win` to create the script and open it in vim editor and write the command `cat /flag` in it, then also make it executable by using `chmod u+x win` then we need to add it to the `PATH` but we need to be careful while changing `PATH` so we just check what `PATH` contains using `echo $PATH` and also copy it while modifiying `PATH` so the final command we enter to modify `PATH` is `PATH="/run/challenge/bin:/run/workspace/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/home/hacker"` to add the directory that `win` is in so that it can be ran. Now finally we run `/challenge/run` and get the flag. 

**Flag Obtained:**
> *pwn.college{o47Xqophlc_iG-O9Pq3kYuJj0aQ.ddzNyUDLwMTN0czW}*

# Processes and Jobs
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Listing Processes
**Commands used:**
- `ps`  : Used to list the processes running in your terminal   

**Thought Process:**
- Need to find the correct program to run, but since it is already running we can find it by using `ps` command and run the correct program to get the flag. `ps` command alone doesnt show any usefull processes so we pair it with the arguments `-ef` or `-aux` to get more information from it.

**Solution:**
- Start the challenge, input the command `ps -aux` to view all the programs running and find the one needed, we observe that the renamed program is `/challenge/15572-run-9513`, so run the program to get the flag.

**Flag Obtained:**
> *pwn.college{cK1G3oZjDqQrvW_V0C_xPNIHwmE.dhzM4QDLwMTN0czW}*

## Killing Processes
**Commands used:**
- `kill PID`  : Used to terminate a process with the specified PID   

**Thought Process:**
- Need to terminate the `/challenge/dont_run` process so that `/challenge/run` can run, so we do that by first finding the PID of `/challenge/dont_run` so that we can terminate it using the `kill` command and thus get the flag. 

**Solution:**
- Start the challenge, input the command `ps -aux` to view all the running processes and find the PID of `/challenge/dont_run`, we find that its PID is "73" so we now terminate it using the command `kill 73`, now we can run `/challenge/run` and get the flag. 

**Flag Obtained:**
> *pwn.college{cHfrD9udJY_wvwVX0R_GwolZex8.dJDN4QDLwMTN0czW}*

## Interrupting Processes
**Commands used:**
- `Ctrl + c`  : Used to interrupt whatever application is waiting on input from the terminal thus causing the application to cleanly exit  

**Thought Process:**
- Need to interrupt `/challenge/run` to get the flag, so we do that by pressing `Ctrl + c` and get the flag.

**Solution:**
- Start the challenge, run the program `/challenge/run`, now to interrupt it press `Ctrl + c` and get the flag.

**Flag Obtained:**
> *pwn.college{YMSckx4YVB2dMb9FiyKdMwS1ME6.dNDN4QDLwMTN0czW}*

## Suspending Processes
**Commands used:**
- `Ctrl + z`  : Used to suspend processes to the background   

**Thought Process:**
- Need to have 2 `/challenge/run` running at the same time to get the flag, we do this by running one program then suspending it to the background using `Ctrl + z` and then running it again thus having 2 of them running at the same time and get the flag.

**Solution:**
- Start the challenge, input the command `/challenge/run` to run the program then press `Ctrl + z` to suspend it and then the run the program again using `/challenge/run` thus getting the flag since we have 2 of them running at the same time.

**Flag Obtained:**
> *pwn.college{oWw4qpSKH_MLTQ5V8yYQxZ4w9d2.dVDN4QDLwMTN0czW}*

## Resuming Processes
**Commands used:**
- `fg`  : Used to resume a suspended process i.e bring it to the foreground  

**Thought Process:**
- Need to suspend and resume `/challenge/run` to get the flag, we do that by using `Ctrl + z` and `fg`.

**Solution:**
- Start the challenge, input the command `/challenge/run` to run the program then suspend it by pressing `Ctrl + z` and then resume it again by using command `fg` and get the flag.

**Flag Obtained:**
> *pwn.college{cIq5JAWDSPPOVX9GN9SgWSJ4d7c.dZDN4QDLwMTN0czW}*

## Backgrounding Processes
**Commands used:**
- `>`  : Used to   

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## Foregrounding Processes
**Commands used:**
- `>`  : Used to   

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## Starting Backgrounded Processes
**Commands used:**
- `>`  : Used to   

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

## Process Exit Codes
**Commands used:**
- `>`  : Used to   

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command

**Flag Obtained:**
> **

# Practicing Piping
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Redirecting output
**Commands used:**
- `>`  : Used to redirect stdout to files  

**Thought Process:**
- Need to use input redirection to write the word "PWN" to the file "COLLEGE" to get the flag.

**Solution:**
- Start the challenge, input the command `echo PWN > COLLEGE` to write "PWN" in "COLLEGE" and get the flag.

**Flag Obtained:**
> *pwn.college{ES30SirLJDsTwr8uGZX58hU2iiE.dRjN1QDLwMTN0czW}*

## Redirecting more output
**Commands used:**
- `>`  : Used to redirect stdout to files   

**Thought Process:**
- Need to redirect the output of `/challenge/run` to a file "myflag" to get the flag so use input redirection.

**Solution:**
- Start the challenge, input the command `/challenge/run > myflag` to write the output of the command to "myflag" and then read the file using `cat myflag` to get the flag.  

**Flag Obtained:**
> *pwn.college{8O1toUWK4NQSMmkRHNoRTM2lE-9.dVjN1QDLwMTN0czW}*

## Appending output
**Commands used:**
- `>>`  : Used to append stdout to files    

**Thought Process:**
- Need to run `/challenge/run` with an append-mode redirect of the output to the file "/home/hacker/the-flag" so as to not the delete the first half of the flag already in the file, so append using `>>`. 

**Solution:**
- Start the challenge, input the command `/challenge/run >> /home/hacker/the-flag` to append the second half of the flag to the file and then use `cat the-flag` to read the file and get the flag.

**Flag Obtained:**
> *pwn.college{c5BfynR2lDQStbGAJngqrv-_qMu.ddDM5QDLwMTN0czW}*

## Redirecting errors
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Redirecting input
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Grepping stored results
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Grepping live output
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Grepping errors
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Duplicating piped data with tee
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Writing to multiple programs
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

## Split-piping stderr and stdout
**Commands used:**
- `cmnd`  : Used to  

**Thought Process:**
- Need to

**Solution:**
- Start the challenge, input the command   

**Flag Obtained:**
> **

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
- `2>`  : Used to redirect stderr to files 

**Thought Process:**
- Need to  redirect the output of `/challenge/run` to "myflag" and the "errors" to file "instructions", so use input redirection to do this and get the flag.

**Solution:**
- Start the challenge, input the command `/challenge/run > myflag 2> instructions` to redirect the output i.e the flag to "myflag" and the error to "instructions", and then use `cat myflag` to read the file and get the flag.

**Flag Obtained:**
> *pwn.college{cEUjN8hlXUI5JZR7trSvIPMMxTQ.ddjN1QDLwMTN0czW}*

## Redirecting input
**Commands used:**
- `<`  : Used to redirect stdin to files

**Thought Process:**
- Need to redirect the "PWN" file to `/challenge/run` and have the "PWN" file contain the value "COLLEGE", so use input redirection to do this and get the flag.

**Solution:**
- Start the challenge, input the command `echo COLLEGE > PWN` to write the value in "PWN" and then use the command `/challenge/run < PWN` to redirect the "PWN" file to `/challenge/run` and get the flag.

**Flag Obtained:**
> *pwn.college{g5EeKwtVoXVCQ3pEwVywgGAYTTD.dBzN1QDLwMTN0czW}*

## Grepping stored results
**Commands used:**
- `>`     : Used to redirect stdout to files
- `grep`  : Used to search for a particular string in files  

**Thought Process:**
- Need to redirect the output of `/challenge/run` to "/tmp/data.txt", do that using input redirection and find the flag in the file using `grep`.

**Solution:**
- Start the challenge, input the command `/challenge/run  > /tmp/data.txt` to redirect the output to the required file and then use the command `grep "pwn.college" /tmp/data.txt` to find the flag in the file.  

**Flag Obtained:**
> *pwn.college{wJ2idMfkYXFcoqgRMF5rbWImPDw.dhTM4QDLwMTN0czW}*

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

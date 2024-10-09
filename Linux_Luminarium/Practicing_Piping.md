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
- `|`  : Used to redirect the standard output from the command to the left of the pipe to standard input of the command to the right of the pipe 

**Thought Process:**
- Need to run `/challenge/run` and `grep` the output to find the flag.

**Solution:**
- Start the challenge, input the command `/challenge/run | grep "pwn.college"` to run the program and find the flag in the output.   

**Flag Obtained:**
> *pwn.college{cuzKk7V2X_y5I9rpt2UI_gxjmsN.dlTM4QDLwMTN0czW}*

## Grepping errors
**Commands used:**
- `>&`  : Used to redirect a file descriptor to another file descriptor

**Thought Process:**
- Need to run `/challenge/run` and `grep` the output to find the flag, but will have to redirect the stderr to stdout to be able to pass it in the `|` command so use `>&` to covert it and run the program to get the flag.

**Solution:**
- Start the challenge, input the command `/challenge/run 2>&1 | grep "pwn.college"` to run the program, convert stderr to stdout and find the flag in the output.   

**Flag Obtained:**
> *pwn.college{ECwTUas9MJ6HpuzcJp4cYYHHtla.dVDM5QDLwMTN0czW}*

## Duplicating piped data with tee
**Commands used:**
- `tee`  : Used to duplicate data flowing through your pipes to any number of files provided on the command line 

**Thought Process:**
- Need to pipe `/challenge/pwn` into `/challenge/college` but doing it directly doesnt work, so we need to check the stdout by `/challenge/pwn` to find out whats the error so that we can fix it and get the flag, we can do this using the `tee` command.

**Solution:**
- Start the challenge, input the command `/challenge/pwn | tee output | /challenge/college` to intercept the command, input `cat output` to see what the stdout is and figure out how to fix this, we find that if we use the argument `--secret I4nN9pKa` it will give the flag so we run the command `/challenge/pwn --secret I4nN9pKa | /challenge/college` and get the flag.

**Flag Obtained:**
> *pwn.college{I4nN9pKaMAbLIwpdzk-I5rfL8u0.dFjM5QDLwMTN0czW}*

## Writing to multiple programs
**Commands used:**
- `>()`  : Used to create a temporary file that can be read   

**Thought Process:**
- Need to pipe the output from `/challenge/hack` to 2 commands `/challenge/the` and `/challenge/planet`, we do this by using `>()` and thus get the flag.

**Solution:**
- Start the challenge, input the command `/challenge/hack | tee >(/challenge/the) | /challenge/planet` to pipe the command and thus get the flag.  

**Flag Obtained:**
> *pwn.college{wT8scWh6SaYNxpnqXJQ2P0s71p7.dBDO0UDLwMTN0czW}*

## Split-piping stderr and stdout
**Commands used:**
- `2>`   : Used to redirect stderr to files
- `|`    : Used to redirect the standard output from the command to the left of the pipe to standard input of the command to the right of the pipe
- `>()`  : Used to create a temporary file that can be read   

**Thought Process:**
- Need to run `/challenge/hack` this produces data on stdout and stderr, we need to provide stderr to `/challenge/the` and the stdout to `/challenge/planet` to get the flag, we do this by combining all our previous knowledge.

**Solution:**
- Start the challenge, input the command `/challenge/hack 2> >(/challenge/the) | /challenge/planet` to satisfy the conditions and thus get the flag.   

**Flag Obtained:**
> *pwn.college{IT_yZ4RuBx4g9YY2boSWPRqXbmL.dFDNwYDLwMTN0czW}*

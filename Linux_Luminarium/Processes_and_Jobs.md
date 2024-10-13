# Processes and Jobs
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


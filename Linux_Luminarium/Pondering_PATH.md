# Chaining Commands
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Chaining with Semicolons
**Commands used:**
- `c`  : Used to

**Thought Process:**
- Need to run `/challenge/pwn` and then `/challenge/college`, chaining them with a semicolon to get the flag.

**Solution:**
- Start the challenge, input the command `/challenge/pwn;/challenge/college` to chain them and get the flag.  

**Flag Obtained:**
> *pwn.college{MgS5isnKKLvyTnaIqVc5-6xlhpU.dVTN4QDLwMTN0czW}*

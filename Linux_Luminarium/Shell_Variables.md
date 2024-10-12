# Shell Variables
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## Printing Variables
**Commands used:**
- `$variable`  : Used to call the variable 

**Thought Process:**
- Need to read the variable "FLAG" to obtain the flag, so we read it by using `echo` and calling it using `$`.

**Solution:**
- Start the challenge, input the command `echo $FLAG` to call and read the variable "FLAG" and get the flag.

**Flag Obtained:**
> *pwn.college{cEuwFi_Q6ASDh_pSA4a8TiMrNrU.ddTN1QDLwMTN0czW}*

## Setting Variables
**Commands used:**
- `variable_name=variable_value`  : Used to define a variable

**Thought Process:**
- Need to define a variable "PWN" and assign it the value "COLLEGE" to get the flag, so we do that by using `=`.

**Solution:**
- Start the challenge, input the command `PWN=COLLEGE` to define the variable and get the flag.

**Flag Obtained:**
> *pwn.college{8Q_0i_lvyPSjc4Iqx6IC-RdxaFX.dlTN1QDLwMTN0czW}*

## Multi-word Variables
**Commands used:**
- `variable_name="variable value"`  : Used to define a variable with multiple words 

**Thought Process:**
- Need to define a variable "PWN" and assign it the value "COLLEGE YEAH" to get the flag, so we do that by using `=` and `" "` because `" "` allows multiple character inputs. 

**Solution:**
- Start the challenge, input the command `PWN="COLLEGE YEAH"` to define the variable and get the flag.

**Flag Obtained:**
> *pwn.college{Y-Sdqzq67oHTEjdJ2-QTcQ40i13.dBjN1QDLwMTN0czW}*

## Exporting Variables
**Commands used:**
- `export variable_name`  : Used to export variables

**Thought Process:**
- Need to invoke `/challenge/run` with the "PWN" variable exported and set to the value "COLLEGE" and the "COLLEGE" variable set to the value "PWN" but not exported, so we create both the variables using `=` and export the "PWN" variable using `export` and then run the command to get the flag.

**Solution:**
- Start the challenge, input the command `COLLEGE=PWN` to define the first variable and use the command `export PWN=COLLEGE` to define the second variable and export it, then run the porgram using `/challenge/run` to get the flag since all conditions ar ssatisfied.

**Flag Obtained:**
> *pwn.college{IMVVVX-AewdZE5GoUzDkNIFbRl4.dJjN1QDLwMTN0czW}*

## Printing Exported Variables
**Commands used:**
- `>`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command 

**Flag Obtained:**
> **

## Storing Command Output
**Commands used:**
- `>`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command 

**Flag Obtained:**
> **

## Reading Input
**Commands used:**
- `>`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command 

**Flag Obtained:**
> **

## Reading Files
**Commands used:**
- `>`  : Used to 

**Thought Process:**
- Need to 

**Solution:**
- Start the challenge, input the command 

**Flag Obtained:**
> **

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
- Start the challenge, input the command `COLLEGE=PWN` to define the first variable and use the command `export PWN=COLLEGE` to define the second variable and export it, then run the porgram using `/challenge/run` to get the flag since all conditions are satisfied.

**Flag Obtained:**
> *pwn.college{IMVVVX-AewdZE5GoUzDkNIFbRl4.dJjN1QDLwMTN0czW}*

## Printing Exported Variables
**Commands used:**
- `env`  : Used to print out every exported variable set in your shell 

**Thought Process:**
- Need to use `env` command to print out all the exported variables and search through them to find the "FLAG" variable to get the flag.

**Solution:**
- Start the challenge, input the command `env` to print all exported variables, on looking through them we find the "FLAG" variable which contains the flag.

**Flag Obtained:**
> *pwn.college{c2nsHqG__1h0x98wAS2D97lZGRu.dhTN1QDLwMTN0czW}*

## Storing Command Output
**Commands used:**
- `$()`  : Used to store the output of a command into a variable

**Thought Process:**
- Need to read the output of the `/challenge/run` command directly into a variable called "PWN" to get the flag, so we do that using `$()` (command substitution).

**Solution:**
- Start the challenge, input the command `PWN=$(/challenge/run)` to read the output of `/challenge/run` (the flag) into "PWN", then use the command `echo $PWN` to print the variable and get the flag.

**Flag Obtained:**
> *pwn.college{wPYQ8aoFR0YBNaHpGpLuRK9_I17.dVzN0UDLwMTN0czW}*

## Reading Input
**Commands used:**
- `read`  : Used to read input from the user

**Thought Process:**
- Need to set the "PWN" variable to the value "COLLEGE" we do this using `read` to get the flag.

**Solution:**
- Start the challenge, input the command `read PWN` to read input to the "PWN" variable, as input write "COLLEGE" to satisfy the conditions and get the flag.

**Flag Obtained:**
> *pwn.college{g18PKSh3J5CpzGg2TdFYEQ7KkcI.dhzN1QDLwMTN0czW}*

## Reading Files
**Commands used:**
- `read variable_name < file`  : Used to read a file into the variable

**Thought Process:**
- Need to to read `/challenge/read_me` into the "PWN" variable to get the flag, so we do this by using `read var_name < file` here `<` directs the "file" as the standard input to `read` which then reads it into the variable. 

**Solution:**
- Start the challenge, input the command `read PWN < /challenge/read_me` to direct the file `/challenge/read_me` as stdin to `read` which reads it to "PWN" and thus satisfy all the conditions and get the flag. 

**Flag Obtained:**
> *pwn.college{MOelQf4uHvLbHNzoS1gBZI5V-ba.dBjM4QDLwMTN0czW}*

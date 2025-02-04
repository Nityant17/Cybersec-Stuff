# Your First Program

- Assembly basic format: Operation Operand Operand...

**Operands:**
- data we give as part of instruction
- data stored in registers
- data in memory storage

**Operations:**
- ADD
- SUBtract
- MULtiply
- DIVide
- MOVe
- MOVe Sign eXtended
- CoMPare
- TEST
- INCrement
- DECrement
- eXCHanGe

## Your First Register

Had to move value '60' into `rax` register so did that

```asm
mov rax,60
```

with this i got the **Flag:** `pwn.college{YfQkFRrWYaAGjYCFLqNbW6QsW3P.dNDN4UDLwMTN0czW}`

## Your First Syscall

Had to do a system call to safely stop the code, learned there are different types of `syscalls` but the one we are using in the challenge is `exit` which is represented by number '60' so moved that value into the register and did a system call

```asm
mov rax,60
syscall
```

with this i got the **Flag:** `pwn.college{4XMN8h1CNQo9YWVddxbG72SxgP2.dhjN4UDLwMTN0czW}`

## Exit Codes

Had to exit with an exit code of '42' so added the exit code to the `rdi` register which stores the exit code value

```asm
mov rdi,42
mov rax,60
syscall
```

with this i got the **Flag:** `pwn.college{ElgrLUj9VTeCMIBitRdTcJevYR7.dBzN4UDLwMTN0czW}`

## Building Executables



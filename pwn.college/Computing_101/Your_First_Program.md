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

Had to exit with an exit code of '42' so added the exit code to the `rdi` register which passes the first parameter to a system call and in this case stores the exit code value

```asm
mov rdi,42
mov rax,60
syscall
```

with this i got the **Flag:** `pwn.college{ElgrLUj9VTeCMIBitRdTcJevYR7.dBzN4UDLwMTN0czW}`

## Building Executables

Had to assemble the code ourselves for this challenge. So started by specifying the type of assembly syntax we are using i.e `.intel_syntax noprefix` and also specifying where the assembler should start assembling the code from

```asm
.intel_syntax noprefix
.global _start
_start:
mov rdi,42
mov rax,60
syscall
```

Now assembled the assembly code into a binary then to an executable using `as` and `ld`

```bash
~$ as -o asm.o code.s
~$ ld -o exe asm.o
~$ ./exe
```

with this i got the **Flag:** `pwn.college{oorUkNvkKN8BjkaH6ntLhEtpJVz.QXwcjMwEDLwMTN0czW}`

## Moving Between Registers

Had to exit with the secret exit code which was stored in `rsi` register which is basically just used for storing values (it also passes the second parameter to system call), so i moved the value from `rsi` to `rdi` to change the exit code

```asm
.intel_syntax noprefix
.global _start
_start:
mov rdi,rsi
mov rax,60
syscall
```

with this i got the **Flag:** `pwn.college{QcmMQgYqzYCkWpVFthlO5aKSS6j.dlDN1YDLwMTN0czW}`

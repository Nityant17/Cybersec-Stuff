# Obedient Cat

**Flag:** `picoCTF{s4n1ty_v3r1f13d_f28ac910}`

Started the challenge, downloaded the file, read it and got the flag!!!

# Super SSH

**Flag:** `picoCTF{s3cur3_c0nn3ct10n_45a48857}`

Need to ssh as "ctf-player" to "titan.picoctf.net" at port "58532" to get the flag with password "1db87a14", so i do that by using the command
```
ssh ctf-player@titan.picoctf.net -p 58532
```
and get the flag!!!

# what's a net cat?

**Flag:** `picoCTF{nEtCat_Mast3ry_3214be47}`

Need to use netcat (nc) to connect to "jupiter.challenges.picoctf.org" at port "41120" to get the flag, so we do that by using the command
```
nc jupiter.challenges.picoctf.org 41120
```
and get the flag!!!

Learnt what nc command is and how it works

# Warmed Up

**Flag:** `picoCTF{61}`

Need to convert 0x3D (base 16) in decimal (base 10) and wrap in picoCTF for the flag, simple!!!

# 2Warm

**Flag:** `picoCTF{101010}`

Need to convert the number 42 (base 10) to binary (base 2) and wrap in picoCTF for the flag, simple!!!

# Bases

**Flag:** `picoCTF{l3arn_th3_r0p35}`

Given a ciphertext and need to decode and wrap it in picoCTF{} to get the flag, on looking at the challenge name i guessed it was base64 or base32 encoding and just decoded it using an online decoder and got the flag!!!

# Wave a flag

**Flag:** `picoCTF{b1scu1ts_4nd_gr4vy_d6969390}`

Given a file "warm", so first i tried reading it but it was unreadable so then i checked what it was using the `file` command and it said 
```
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=b11c22752c901adc13ba1ce86eda9d5516f22763, with debug_info, not stripped
```
After reading executable, i tried executing it and got the output
```
Hello user! Pass me a -h to learn what I can do!
```
So i passed it with `-h` and got the flag!!!
```
./warm -h
```

# Tab, Tab, Attack

**Flag:** `picoCTF{l3v3l_up!_t4k3_4_r35t!_524e3dc4}`

Got a zip file, unzipped it and used the terminal `cd` command to see whats in it and saw another directory inside it, so i guessed from the challenge name that we probably have to traverse alot of directories so i just used the `tab` key to get to the end directory there i saw a file which i tried to read but was unreadable so then i executed it and ZAP i got the flag!!!

# strings it

**Flag:** `picoCTF{5tRIng5_1T_7f766a23}`

Tried running the "strings" file, it said to try using the `strings` command so i learnt it and ran it and it printed alot of data so i used `grep` to find the flag in the data!!!
```
strings strings | grep "picoCTF"
```

# 

**Flag:** ``

S

# 

**Flag:** ``

S

# 

**Flag:** ``

S

# vault-door-training

**Flag:** `picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}`

Started the challenge and basically it said to check the source code and extract the password from there because that was the flag, so i read the code and the password was simply there so i was able to solve the challenge!!!

# vault-door-1

**Flag:** `picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}`

Read the source code and and found that it checked the password (flag) entered by comparing it to the stored values, so i arranged all the stored characters as per the place checked and got the flag!!!

# vault-door-3

**Flag:** ``

s

# keygenme-py

**Flag:** `picoCTF{1n_7h3_|<3y_of_01582419}`

Started the challenge and knew had to understand the source code to find the flag, so i slowly started reading the code and found out the flag was divided into 3 parts and we knew 2 of those parts and we just had to find the remaining part, now the important part of the code was to solve the way to get the premium access because the rest of the code was nothing important so what the code did was take the input of premium activation key from the user and passed it through a few checks to confirm it and i understoond what checks it did, the first was that it started with the first part of the flag and had the same amount of characters as the flag, then secondly it compared next 8 characters with different positioned values of SHA-256 hash of b"ANDERSON" this gave us the next 8 characters this made a total of 31 and only 1 character was left which replaced } since it felt like this was the flag i tried it annndddd turns out it was!!! 

# Safe Opener

**Flag:** `picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}`

Got the source code file so read it and it showed the ciphered password and it was written base 64 encoder in the code so i just put the ciphered password in a decrypter and got the flag!!!

# Safe Opener 2

**Flag:** `picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_198203f7}`

i just tried to read the file some part was unreadable but the flag was right there completely readable, i didnt expect this to be so easy!!! (just to learn some more i tried a different method and apprantely you can decompile java codes so i did that using an online decoder and that fixed the code and also gave me the flag)


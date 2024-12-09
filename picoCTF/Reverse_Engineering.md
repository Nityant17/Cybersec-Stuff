# vault-door-training

**Flag:** `picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}`

Started the challenge and basically it said to check the source code and extract the password from there because that was the flag, so i read the code and the password was simply there so i was able to solve the challenge!!!

# vault-door-1

**Flag:** `picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}`

Read the source code and and found that it checked the password (flag) entered by comparing it to the stored values, so i arranged all the stored characters as per the place checked and got the flag!!!

# vault-door-3

**Flag:** `picoCTF{jU5t_a_s1mpl3_an4gr4m_4_u_1fb380}`

So again i read the code and tried to understand it, it was basically taking the flag and jumbling it up according to some conditions to get a ciphered flag which it compared to a stored value, so i took the stored value and unjumbled it by reversing all the conditions and steps, this took along time since i did it manually (dont know java language) so it was a bit tedious but the challenge itself was simple and thus i got the flag!!!

# vault-door-4

**Flag:** `picoCTF{jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b}`

Read the code and understood that it was basically converting each character to bytes and comparing it to the bytes of the stored values which were in form of ASCII, hex, octal and just normal text so i converted all the stored values to text and put them together to get the flag!!!

# vault-door-5 

**Flag:** `picoCTF{c0nv3rt1ng_fr0m_ba5e_64_84fd5095}`

Read the code and found out it was just first URL encoding the flag and then base64 encoding to compare to the stored value so i just took the stored value gave it to a base64 decoder and then gave that to a URL decoder to get the flag!!!

- [base64 decoder](https://www.base64decode.org/)
- [URL decoder](https://www.urldecoder.org/)

# vault-door-6

**Flag:** `picoCTF{n0t_mUcH_h4rD3r_tH4n_x0r_948b888}`

Basically the code just took each character of the flag and XORed it with `0x55` and then subtracted it with the stored values and if it was not equal to 0 it retruned false that meant on XORing each character of the flag we are basically getting the stored values so i just took the stored values gave it to chatGPT and asked it to XOR all of them with `0x55` (since XOR is reversible) and convert those values to text to finally get the flag!!!

# vault-door-7

**Flag:** `picoCTF{A_b1t_0f_b1t_sh1fTiNg_dc80e28124}`

Read the code and understood that this was basically taking 4 characters at a time converting them to ASCII then to binary putting them together and then converting this set of 32 bits into a int and then comparing to stored ints so i took those stored ints gave it to ChatGPT to convert them to binary then asked it to convert the binary to ASCII but the free version ended so it couldnt do that so then i manually turned all the binaries to ASCII then to text and finally got the flag!!! (i dont know why but the last 2 ints were 9 numbers in length instead of 10 so they gave me 31 bits this took alot of time to fgure out how to divide the bits to convert to decimal and after few hours i realized i just had to add a 0 to the starting of the binary to be able to divide them equally :( )

- [Binary to Decimal](https://www.mathsisfun.com/binary-decimal-hexadecimal-converter.html)
- [ASCII Table](https://www.asciitable.com/)

# vault-door-8

**Flag:** `picoCTF{s0m3_m0r3_b1t_sh1fTiNg_2e762b0ab}`

Read the code and understood a few parts of this code but i knew i couldnt solve this manually (it was switching bits by masking them and bit shifting them this would have taken ages to solve by hand), i had to just use the code and reverse the switchbits called by just reordering the calls in reverse and giving the stored values as input to solve it but i dont know java so used blackbox.ai to help me reverse the code and then i ran it on an online compiler and voila i got the flag!!!

# keygenme-py

**Flag:** `picoCTF{1n_7h3_|<3y_of_01582419}`

Started the challenge and knew had to understand the source code to find the flag, so i slowly started reading the code and found out the flag was divided into 3 parts and we knew 2 of those parts and we just had to find the remaining part, now the important part of the code was to solve the way to get the premium access because the rest of the code was nothing important so what the code did was take the input of premium activation key from the user and passed it through a few checks to confirm it and i understoond what checks it did, the first was that it started with the first part of the flag and had the same amount of characters as the flag, then secondly it compared next 8 characters with different positioned values of SHA-256 hash of b"ANDERSON" this gave us the next 8 characters this made a total of 31 and only 1 character was left which replaced } since it felt like this was the flag i tried it annndddd turns out it was!!! 

# Safe Opener

**Flag:** `picoCTF{pl3as3_l3t_m3_1nt0_th3_saf3}`

Got the source code file so read it and it showed the ciphered password and it was written base 64 encoder in the code so i just put the ciphered password in a decrypter and got the flag!!!

# Safe Opener 2

**Flag:** `picoCTF{SAf3_0p3n3rr_y0u_solv3d_it_198203f7}`

i just tried to read the file some part was unreadable but the flag was right there completely readable, i didnt expect this to be so easy!!! (just to learn some more i tried a different method and apprantely you can decompile java codes so i did that using an online decoder and that fixed the code and also gave me the flag)

# ARMssembly 0

**Flag:** `picoCTF{f51e846f}`

started the challenge and opened the given ARM assembly but was not able to understand much but i saw `.arch armv8-a` on the starting of the code so i asked chatGPT to tell me how to run these type of assemblies and found out that i cant directly run these type of codes as my device is a non-ARMv8 machine so i need to first use a cross compiler so i installed `binutils-aarch64-linux-gnu` and `gcc-aarch64-linux-gnu` then i used `aarch64-linux-gnu-as -o ch.o chall.S` and `aarch64-linux-gnu-gcc -static -o ch ch.o` to assemble the code and get an executable binary file `ch` but to i wasnt able to execute it directly so i installed `qemu-user-static` to make non compatibile binaries executable and thus i was able to run and the file `./ch 4112417903 1169092511` which gave the output `Result: 4112417903` which i then converted to hex format as specified and got the flag!!!

-[Steps to run ARMv8 assembly](https://github.com/joebobmiles/ARMv8ViaLinuxCommandline)

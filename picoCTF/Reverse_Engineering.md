# vault-door-training

**Flag:** `picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}`

Started the challenge and basically it said to check the source code and extract the password from there because that was the flag, so i read the code and the password was simply there so i was able to solve the challenge!!!

# keygenme-py

**Flag:** `picoCTF{1n_7h3_|<3y_of_01582419}`

Started the challenge and knew had to understand the source code to find the flag, so i slowly started reading the code and found out the flag was divided into 3 parts and we knew 2 of those parts and we just had to find the remaining part, now the important part of the code was to solve the way to get the premium access because the rest of the code was nothing important so what the code did was take the input of premium activation key from the user and passed it through a few checks to confirm it and i understoond what checks it did, the first was that it started with the first part of the flag and had the same amount of characters as the flag, then secondly it compared next 8 characters with different positioned values of SHA-256 hash of b"ANDERSON" this gave us the next 8 characters this made a total of 31 and only 1 character was left which replaced } since it felt like this was the flag i tried it annndddd turns out it was!!! 

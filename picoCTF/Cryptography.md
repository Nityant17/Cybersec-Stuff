# C3

**Flag:** `picoCTF{adlibs}`

Approach:

- **Step 1**

So i started by first using chatGPT to understand the encoding code and see how the code works

encoding code:
```
import sys
chars = ""
from fileinput import input
for line in input():
  chars += line

lookup1 = "\n \"#()*+/1:=[]abcdefghijklmnopqrstuvwxyz"
lookup2 = "ABCDEFGHIJKLMNOPQRSTabcdefghijklmnopqrst"

out = ""

prev = 0
for char in chars:
  cur = lookup1.index(char)
  out += lookup2[(cur - prev) % 40]
  prev = cur

sys.stdout.write(out)
```
What i found out was that the code was a cyclical encoder and basically what the code was doing is taking the message and finding its index in "lookup1" and then based on the index replacing it with a value from "lookup2" and how was it deciding what vales to switch? We find that by understanding the `for` loop, it was taking the index value of the current character (stored in "cur") and subtracting it from the index value of previous character (stored in "prev") and then taking its remainder by dividing from 40 then this value was used as the new index in "lookup2" and replaced

- **Step 2**

After understanding the code we need to write the decoding code of it and to do that we need to get a full grasp on its working, i did that by manually encoding "hello" using this method and seeing how exactly the index values changed and how we could decode it so on encoding i got the values "brHAD" and seeing the relationships between all the indexes i managed to make a connection and find the way to decode it, we could decode the message by taking the index of the character in encoded message in "lookup2" adding the index of previous decoded chracater in "lookup1" to it and dividing by 40 and getting the remainder to get the current encoded characters index in "lookup1" and find its decoded alternative

decoding code:
```
import sys
chars = ""
from fileinput import input
for line in input():
  chars += line

lookup1 = "\n \"#()*+/1:=[]abcdefghijklmnopqrstuvwxyz"
lookup2 = "ABCDEFGHIJKLMNOPQRSTabcdefghijklmnopqrst"

out = ""

prev = 0
for char in chars:
  cur = lookup2.index(char)
  d = (cur + prev) % 40
  out += lookup1[(cur + prev) % 40]
  prev = d

sys.stdout.write(out)
```

- **Step 3**

Now we run the decoding code on the terminal
```
cat ciphertext | python3 convert1.py
```
where "ciphertext" is the encoded message and "convert1.py" is the decoding code and on running this we get the output
```
#asciiorder
#fortychars
#selfinput
#pythontwo

chars = ""
from fileinput import input
for line in input():
    chars += line
b = 1 / 1

for i in range(len(chars)):
    if i == b * b * b:
        print chars[i] #prints
        b += 1 / 1
```
now we have to decode this

- **Step 4**

On examining this output we can undertsand that the code is basically asking to run the code with itself as input and using `python2`, so we do that 
```
cat ciphertext | python3 convert1.py > p.py
cat p.py | python2 p.py
```
on using these we get the output
```
a
d
l
i
b
s
```
which is the flag!!!


Knowledge Gained:

1. How to examine encoding codes and understand their working
2. How to make a decoder from an encoder
3. Difference between python3 and python2

Incorrect methods:

- In the starting i messed up indexing by not including " " while encoding "hello"
- While writing the decoding code in value of "d" i used [  ] as brackets which made it a list and led to type error 
- Was stuck on the second code for a long time didnt know what to do with the decoded code and had many failed attempts to solve it

References

- [chatGPT](chatgpt.com)

# miniRSA

**Flag:** `picoCTF{n33d_a_lArg3r_e_d0cd6eae}`

Approach:

- **Step 1**

So i started by first understanding RSA using wikipedia and i understand the basic encryption method of RSA and the various terms used in its encryption such as "d" (private decryption key), "e and n" (public encryption keys), "m and c" (decoded and encoded message) and also the relation between all of them, n=p*q where p and q are 2 prime nummbers, φ(n)=(p-1)(q-1) and (d*e)%φ(n)=1 and the encoded message is c=[m^(e)]%n and decoded message is m=[c^(d)]%n

- **Step 2**

Now to decode it we are given the values of "n", "c" and "e" and we can see that value of "e" is really small, 3 which makes this vulnerable to "small e attack" so we exploit this fact and decode this RSA encryption, small e attack basically means that because the value of "e" is really small we can decrypt the message without the need of "d" because during encrypting the formula is "c=[m^(e)]%n" so here it will be [m^3]%n which will ultimately be equal to m^3 so we can just cube root "c" to get the flag

- **Step 3**

Sine we have value of "c" we just cube root and get the flag!!! But the "c" given was really big and and not in array format so i used an online decoder to decode it and finally get the flag!!!

![image](https://github.com/user-attachments/assets/3743fae5-f51e-4058-806b-43837d2c2831)


Knowledge Gained:

1. Working of RSA encryption and decryption
2. What is small "e" attack and how to do it

Incorrect methods:

- I didnt understand how to cube root the large and single value of "c" given so i had many failed attempts 

References

- [Wikipedia](https://en.wikipedia.org/wiki/RSA_(cryptosystem))
- [Decoder](https://www.dcode.fr/rsa-cipher)
- [How to small e attack](https://amsghimire.medium.com/low-exponent-attack-511bf5d227fc)

# Custom encryption

**Flag:** `picoCTF{custom_d2cr0pt6d_019c831c}`

Approach:

- **Step 1**

Again i started by using ChatGPT to learn the working of the code

encoding code:
```
from random import randint
import sys

def generator(g, x, p):
    return pow(g, x) % p

def encrypt(plaintext, key):
    cipher = []
    for char in plaintext:
        cipher.append(((ord(char) * key*311)))
    return cipher

def is_prime(p):
    v = 0
    for i in range(2, p + 1):
        if p % i == 0:
            v = v + 1
    if v > 1:
        return False
    else:
        return True

def dynamic_xor_encrypt(plaintext, text_key):
    cipher_text = ""
    key_length = len(text_key)
    for i, char in enumerate(plaintext[::-1]):
        key_char = text_key[i % key_length]
        encrypted_char = chr(ord(char) ^ ord(key_char))
        cipher_text += encrypted_char
    return cipher_text

def test(plain_text, text_key):
    p = 97
    g = 31
    if not is_prime(p) and not is_prime(g):
        print("Enter prime numbers")
        return
    a = randint(p-10, p)
    b = randint(g-10, g)
    print(f"a = {a}")
    print(f"b = {b}")
    u = generator(g, a, p)
    v = generator(g, b, p)
    key = generator(v, a, p)
    b_key = generator(u, b, p)
    shared_key = None
    if key == b_key:
        shared_key = key
    else:
        print("Invalid key")
        return
    semi_cipher = dynamic_xor_encrypt(plain_text, text_key)
    cipher = encrypt(semi_cipher, shared_key)
    print(f'cipher is: {cipher}')

if __name__ == "__main__":
    message = sys.argv[1]
    test(message, "trudeau")
```
So basically how the code works is by encoding the flag using two differenct methods using some keys it generated at random so to decode we basically just need the keys and have to reverse the process.

- **Step 2**

But first we need to fully understand the code, the code has different functions that do different things the main one is `test` it starts the encryption process. It first takes in values of "p" and "g" and checks if they are prime or not using `is_prime`, if they arent prime it retakes their values here in our case the values are "p=97" and "g=31" both are prime. Now it moves on to key generation for which it randomly generates "a" and "b" (luckily we know the value of them used for encoding) and uses them to generate "u" and "v" using `generator` (which basically takes in three parameters and puts them in the formula (g^x)%p and returns the value), so we now have values of "u" and "v" which are used to generate the "key" and "b_key" again by using `generator` and if both have equal values then "shared_key" is assigned the value of "key". Now all the keys are generated and it starts the encoding by first getting a semi ciphertext by using the `dynamic_xor_encrypt` which takes in the "flag" and a "text_key" (given while running `test` ("trudeau")) then it reverses the "flag" and XOR's each character of the "flag" with its corressponding character in "text_key" to get the semi cipher. Finally it takes the semi cipher and gives it to `encrypt` along with the "shared_key" which basically takes each character from semi cipher converts it to ASCII then multiplies it with the "shared_key" and 311 then appends the number to a list "cipher" which is the final ciphertext.   

- **Step 3**

Now we finally start the decoding process, to decode this we need to first generate the same keys used (this is easy since we have "a" and "b" we can just use the `generator` function to get the keys). After this we need to undo the `encrypt` encryption to get the semi cipher from final cipher (this is done by dividing each number in ciphertext list by the key generated and 311 to get the ASCII values then using `chr` to convert to string), now that we have the semi cipher we need to undo the XOR encryption, luckily XOR is reversible so we use this fact to decrypt it, then we just reverse the decrypted answer and get the flag!!!

decoding code:
```
from random import randint

def generator(g, x, p):
    return pow(g, x, p)

def decrypt(cipher, key):
    decrypted_text = ""
    for num in cipher:
        char_code = num // (key * 311)
        decrypted_text += chr(char_code)
    return decrypted_text

def dynamic_xor_decrypt(cipher_text, text_key):
    decrypted_text = ""
    key_length = len(text_key)
    for i, char in enumerate(cipher_text):
        key_char = text_key[i % key_length]
        decrypted_char = chr(ord(char) ^ ord(key_char))
        decrypted_text += decrypted_char
    return decrypted_text[::-1]

def decode(cipher, a, b, g=31, p=97, text_key="trudeau"):
    u = generator(g, a, p)
    v = generator(g, b, p)
    shared_key = generator(v, a, p)
    semi_cipher = decrypt(cipher, shared_key)
    plaintext = dynamic_xor_decrypt(semi_cipher, text_key)
    return plaintext

ciphered_message = [ list of the ciphertext ] 
a = 88
b = 26
decoded_message = decode(ciphered_message, a, b)
print("Decoded message:", decoded_message)
```
On running this code we get the flag!!!

Knowledge Gained:

1. Working of XOR and how it is reversible
2. Same concepts learned in C3

Incorrect Methods:

- No incoorect method was pretty simple

References

- [chatGPT](chatgpt.com)
- [XOR](https://ctf101.org/cryptography/what-is-xor/)

# Mod 26

**Flag:** `picoCTF{next_time_I'll_try_2_rounds_of_rot13_ulYvpVag}`

We are given the flag in ciphertext with ROT13 applied to it so just decrypt it using ROT13 and get the flag!!!

# substitution0

**Flag:** `picoCTF{5UB5717U710N_3V0LU710N_357BF9FF}`

The cipher was a substitution cipher so i just searched online for a substitution decoder and it didnt work then i read the hint and it said to try using a frequency attack so i used ChatGPT to understand what that was and it suggested that this is basically used to decode caeser ciphers so i searched online for a caeser decoder but that didnt work either so i looked at the cipher and i saw a wierd key like text at the starting of the cipher so i asked if there was verion of caeser cipher that used a key thus i found that this was keyed caeser cipher, so again found an online decoder and voila it worked and gave me the flag!!!

- [Decoder](https://www.boxentriq.com/code-breaking/keyed-caesar-cipher)

#

**Flag:** ``

S

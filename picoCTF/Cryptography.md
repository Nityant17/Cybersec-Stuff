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

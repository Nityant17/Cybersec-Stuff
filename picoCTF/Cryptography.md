# C3

**Flag:** `picoCTF{adlibs}`

Approach:

- step 1

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
What i found out was that basically what the code was doing is taking the message and finding its index in "lookup1" and then based on the index replacing it with a value from "lookup2" and how was it deciding what vales to switch ? We find that by understanding the `for` loop, it was taking the index value of the current character (stored in "cur") and subtracting it from the index value of previous character (stored in "prev") and then taking its remainder by dividing from 40 then this value was used as the new index in "lookup2" and replaced

- step 2

```
terminal output
```


What you learned through solving this challenge:

1. first concept
2. second concept
3. etc.

Other incorrect methods you tried:

- a
- b
- c

References

- [chatGPT](chatgpt.com)

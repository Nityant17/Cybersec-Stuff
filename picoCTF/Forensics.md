# m00nwalk

**Flag:** `picoCTF{beep_boop_im_in_space}`

Approach:

- **Step 1**

I started by downloading the file and saw it was a .wav file which means it was an audio file and knew we had to use a certain decoder for it, then i saw the hints and researched a bit about them by using my trusty companion chatGPT and found out that we needed to use a SSTV decoder for it with an RX setting set to something related to Scottish Dog.

- **Step 2**

I tried really hard to find an online SSTV decoder but was unable to find one ultimatley i downloaded a mobile app which had the decoder and played the audio on my laptop, set RX as scottie 1 and let the app do the magic while my ears bled, and thus i got the picture with the flag!!!

![WhatsApp Image 2024-11-08 at 02 04 23_5f89e5d6](https://github.com/user-attachments/assets/a00ebe72-ed09-4190-ba67-db14464d8aa1)

The picture was a bit unclear but i was able to guess the "im" and "in" part

Knowledge Gained:

1. How did pictures from the moon landing get sent back to Earth
2. Who is the CMU mascot
3. what is SSTV method of transfer 

Incorrect Methods:

- No incorrect methods, what we needed to do was pretty straight forward

References

- [ChatGPT](www.chatgpt.com)
- [Decoder](https://play.google.com/store/apps/details?id=xdsopl.robot36&hl=en_IN)

# Trivial Flag Transfer Protocol

**Flag:** `picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}`

Approach:

- **Step 1**

When i first downloaded the file i saw it was in ".pcapng" format, i had no clue of what this was so as always i used chatGPT to understand it after reading on it i learned that a ".pcapng" file (Packet Capture Next Generation) is a file format used to store network packet data and you can analyze these files by using tshark or wireshark and since tshark was just a linux command i decided to install that instead of wireshark (a big mistake) to analyze the file. 

- **Step 2**

Now with tshark installed i asked chatGPT to tell me how to use tshark and the commands i could use to find the hidden data, i tried alot of various commands and spent alot of hours to finally understand that tshark was not going to work out and i needed to install wireshark to make the file human understandable.

- **Step 3**

After wasting hours of my life i finally installed wireshark and opened the file in it, there i saw that there were different type of protocols being used and one of them was "TFTP", there i understood that TFTP was a type of transfer protocol and not just a challenge name, so then i researched a bit about it and and found that TFTP is used to transfer a file from a client to a server and from a server to a client by using UDP (User Datagram Protocol) and works on port number 69, also it doesnt provide much security and thus is only used on local networks. So after learning this i decided to filter the the data based on TFTP in wireshark, upon doing this i saw that there was a file instructions.txt in the data, so i went to extract it and while extracting i saw there were a few more files that could be extracted so i exctracted all of them.

- **Step 4**

Now with all of the files excrtacted i read "instruction.txt' and it contained a cipher, which in put in ChatGPT and it suggested that it could be ROT13 encoded so i used an online decoder and found that it said
```
FRONTDOORSECURITYAPPROVALREQUESTONCONFIRMATION.FIGUREOUTAWAYTOHIDETHEFLAGANDIWILLCHECKBACKFORTHEPLAN
```
On reading this i knew we had to do something with the "plan" file so next i read that and again found a cipher which on decoding gave
```
IUSEDTHEPROGRAMANDHIDITWITH-DUEDILIGENCE.CHECKOUTTHEPHOTOS
```
Now on reading this i understood that we needed to use the "program" file and do something with the "photos", the "program" file was a ".deb" file, so i googled what it was and found it is used to download stuff on terminal and is unpacked by using `dpkg` so i installed it by using the command
```
sudo dpkg -i program.deb
```
and while installing it showed that what was installed was `steghide` which is a steganography program that is able to hide data in various kinds of image- and audio-files and also uncover it so i learnt how to use this command and found it needs a password which i gues was "DUEDILIGENCE" from the decoded message and ran the command
```
steghide extract -sf ./picture1.bmp -p DUEDILIGENCE
```
this gave me an error
```
steghide: error while loading shared libraries: libjpeg.so.62: cannot open shared object file: No such file or directory
```
which i wasnt able to understand so i put it in chatGPT and it said to install the correct version of `libjpeg` so i did that by using 
```
sudo apt-get install libjpeg62
```
However this did not fix the error and instead gave me the output
```
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
You might want to run 'apt --fix-broken install' to correct these.
The following packages have unmet dependencies:
 steghide : Depends: libjpeg62-turbo (>= 1:1.3.1) but it is not installable
E: Unmet dependencies. Try 'apt --fix-broken install' with no packages (or specify a solution).
```
so then i ran
```
sudo apt --fix-broken install
```
which fixed steghide and finally it was working again so i used steghide 
```
steghide extract -sf ./picture1.bmp -p DUEDILIGENCE
```
got the output
```
steghide: could not extract any data with that passphrase!
```
tried again on the second image and got the same output but when i tried on the third image i got the flag!!!

Knowledge Gained:

1. What is .pcapng file   
2. How to analyze these type of files
3. How to use tshark and wireshark
4. What is TFTP and its working
5. How to filter data in TFTP using opcode
6. What is .deb file and how to install it
7. What is steghide and how to use it 

Incorrect Methods:

- Using tshark instead of wireshark thinking it would be easier and wasting hours

References

- [ChatGPT](www.chatgpt.com)
- [TFTP](https://www.geeksforgeeks.org/what-is-tftp-trivial-file-transfer-protocol/)
- [Wireshark](https://www.wireshark.org/download.html)
- [tshark](https://www.wireshark.org/docs/man-pages/tshark.html)
- [ROT13 Decoder](https://cryptii.com/pipes/rot13-decoder)
- [.deb file](https://en.wikipedia.org/wiki/Deb_(file_format))

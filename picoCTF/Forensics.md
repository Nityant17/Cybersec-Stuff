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

# m00nwalk2

**Flag:** `picoCTF{the_answer_lies_hidden_in_plain_sight}`

So i saw there was another m00nwalk challenge thus i tried this too, this time there 4 files, the main trasnmission file was the same from the previous one but there were more files clue1,2,3. Now i tried using my phone app again but this time it gave me alot of trouble dont know why??, it took a lot of tries, rewinding and eardrums to finally get the photos from the files.

![WhatsApp Image 2024-11-09 at 23 50 13_af88f9a0](https://github.com/user-attachments/assets/ca8b9a2a-cfc0-4a37-bed9-c2a99e997932)

![WhatsApp Image 2024-11-09 at 23 59 34_9cdfbcd5](https://github.com/user-attachments/assets/5b9ade0d-32e8-4235-804f-cb5b59803930)

I just googled Alan Eliasen the future boy and the first thing that showed up was a Steganography Tool, so i knew we had to use a steganography tool to get the flag from the main file, so i used steghide (installed from another challenge) with the password "hidden_stegosaurus" as per the image and got the flag!!! (still dont know what the hint in clue2 (last image) means) 

# Trivial Flag Transfer Protocol

**Flag:** `picoCTF{h1dd3n_1n_pLa1n_51GHT_18375919}`

Approach:

- **Step 1**

When i first downloaded the file i saw it was in ".pcapng" format, i had no clue of what this was so as always i used chatGPT to understand it after reading on it i learned that a ".pcapng" file (Packet Capture Next Generation) is a file format used to store network packet data and you can analyze these files by using tshark or wireshark and since tshark was just a linux command i decided to install that instead of wireshark (a big mistake) to analyze the file. 

- **Step 2**

Now with tshark installed i asked chatGPT to tell me how to use tshark and the commands i could use to find the hidden data, i tried alot of various commands and spent alot of hours to finally understand that tshark was not going to work out and i needed to install wireshark to make the file human understandable.

- **Step 3**

After wasting hours of my life i finally installed wireshark and opened the file in it, there i saw that there were different type of protocols being used and one of them was "TFTP", there i understood that TFTP was a type of transfer protocol and not just a challenge name, so then i researched a bit about it and and found that TFTP is used to transfer a file from a client to a server and from a server to a client by using UDP (User Datagram Protocol) and works on port number 69, also it doesnt provide much security and thus is only used on local networks. So after learning this i decided to filter the the data based on TFTP in wireshark, upon doing this i saw that there was a file instructions.txt in the data, i had a suspicion that we had to extract it for which i went to export objects and selected TFTP there i saw that there were a few more files that could be exported so i exported all of them.

![image](https://github.com/user-attachments/assets/9b556de8-1a48-4acc-9a5b-2d49dad9d4f8)

![image](https://github.com/user-attachments/assets/7c30ee10-7ef0-4d6e-ac95-15245b1ec87f)

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

# tunn3l v1s10n

**Flag:** `picoCTF{qu1t3_a_v13w_2020}`

Approach:

- **Step 1**

So i downloaded the file and tried to open it and it didnt open, the hint said "Weird that it won't display right...", this reminded me of the challenge i solved in OASIS in which we were given a corrupted png and we had to fix its header to get the correct image, so i opened the file using a hex editor and saw the header and compared it to a list of file signatures and found this was a bitmap file and had .bmp extension thus i opened another .bmp picture (one from the previous challenge) and compared the starting hexes and there i saw that our file had 
```
42 4D 8E 26 2C 00 00 00 00 00 BA D0 00 00 BA D0
```
and the other file had
```
42 4D C6 94 0C 00 00 00 00 00 36 00 00 00 28 00
```
Then i just changed all the values to match the other file and voila the image opened

![image](https://github.com/user-attachments/assets/d0b7daeb-2653-4f1e-8784-6db94aaca876)

- **Step 2**

After getting this image i was confused at what to do next, i tried various image proceesing steps like binwalk, exiftool but it led me no where, i spent a few hours but then i had the idea to increase the size of the image since the challenge name was tunnel vision, so i learnt what hex had the value of heigth and width and decided to increase the height (the height of the image was 0132, 306 in decimal and the width was 046E, 1134 in decimal) so i tried a few small values at first and saw it was working and the image was showing more things and finally when i enetered 850 (converted to hex 0352 and entering format 52 03) as the height i got the brand new image which had the flag!!!

![image](https://github.com/user-attachments/assets/f4f31cfa-015e-4c1c-9f87-42953b59855a)

Knowledge Gained:

1. What different file headers look like and what type of file they represent
2. What do different bytes represent in the hex code
3. Sometimes the challenge name contains a clue 

Incorrect Methods:

- Tried using binwalk, exiftool and other various methods to solve the image i got and nothing worked

References

- [ChatGPT](www.chatgpt.com)
- [Hex Editor](https://hexed.it/)
- [decimal and hex converter](https://www.rapidtables.com/convert/number/decimal-to-hex.html?x=850)
- [BMP file format](https://en.wikipedia.org/wiki/BMP_file_format)
- [List of file signatures](https://en.wikipedia.org/wiki/List_of_file_signatures)

# Enhance!

**Flag:** `picoCTF{3nh4nc3d_d0a757bf}`

When i first downloaded the file i saw it was a wierd format so i googled about it and learned that it is a Scalable Vector Graphics file and these can be zoomed in without losing quality, but when i tried doing the enhancing i inspected the file adn there i say the flag in the code of inspect so i didnt even have to do anything to solve the challenge!!!

![image](https://github.com/user-attachments/assets/ba584cfb-48ee-4a64-a9f3-3565a4d75dd3)


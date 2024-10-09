# OASIS Capture The Flag Competition
- This is a writeup on some of the challenges that taught me the most
- Our team got **10th** position and overall this was a very fun experience and i got to learn about alot of new things

## I have been falling for 30 minutes!
### Description:
It hits you! The IOI uses an encrypted communication service to control the virus's every move. Your mission is clear: sever the link between the IOI and the virus to isolate and defeat it. However, you linger too long in one place, and the IOI catches wind of your plan. Fortunately for them, they have a firewall jail just beneath the surface. The ground trembles and splits open, sending you plummeting into the abyss. You land with a resounding THUD, surrounded by towering firewalls. You see a computer in the middle of the cell, and feel like you can use it to your advantage. Can you break free from this digital prison? [firewall](https://firewall.oasis.cryptonite.live)

### Solution:
When you first load up the site you see you can change the user by clicking the arrow buttons in the centre and we notice that affects the "userid=number" in the url. Since the parameters of the url are visible it is more prone to SQL injection attacks, so i tried changing the value of the parameter to something else to check that, I put in the value as "6" and behold the flag appeared.

Flag:
> *OASIS{T00_m4ny_h0urs_4nd_wh3r3_d1d_1t_l34d}*

## All that for a drop of blood
### Description:
As the terminal roars back to life, a single message blinks on the screen: "START GAME." You're no longer just a playerâ€”you're in the endgame now. The keyboard before you looks deceptively simple, but nothing you try gets past the loading screen. Something is clearly wrong. Can you uncover the hidden flaw and push beyond this stagnant start? [Game](https://startgame.oasis.cryptonite.live/)

### Solution: 
When you open the site and click on start game it shows that user needs to be an "OASISPlayer" to play the game so we need to send a "POST" request on "/game" endpoint, we do that using the `curl` command, input `curl -X POST   'https://startgame.oasis.cryptonite.live/game'   -H 'Content-Type: application/json'   -H 'User-Agent: OASISPlayer'   -d '{"errorMessage": "Give me a message"}'`and we get the output `{"errorMessage":"Can you give me the name of the Student Project organizing this event as a url parameter 'name'?"}` 

So we add the parameter and run the command ` curl -X POST   'https://startgame.oasis.cryptonite.live/game?name=cryptonite'   -H 'Content-Type: application/json'   -H 'User-Agent: OASISPlayer'   -d '{"errorMessage": "Give me a message"}'` and we get the output `{"errorMessage":"Do you know you can chain query parameters? Add a 'rank' parameter and give the current CTFTime rank of the project on /givemetheFlag"}`.

So we add the "rank" parameter with the "name" paramenter and change the endpoint to "/givemetheFlag" and send the request again using command ` curl -X POST   'https://startgame.oasis.cryptonite.live/givemetheFlag?name=cryptonite&rank=4'   -H 'Content-Type: application/json'   -H 'User-Agent: OASISPlayer'   -d '{"errorMessage": "Give me a message"}'` and finally we get the flag.

Flag:
> *OASIS{G37_d035_n07_4lw4y5_G37_th1ng5}*

## Keanu crack the matrix
### Description:
Amid the chaos, you spot something crucial: a control unit embedded in the mechanoids'' chassis. With a well-timed leap, you manage to access one of the units. A complex matrix of data awaits you inside, but if you can decipher it, you could seize control of the entire robotic army. Can you crack the code and turn the tables on IOI? [File](https://drive.proton.me/urls/Z5715WJ2ZG#bubCkAYX6dlt)

### Solution:
On seeing the documents we can understand that the code was used to encrypt the flag into a matrix of large numbers using some keys(large prime numbers).

So we need to reverse the encryption process and write a decryption code and also find out the keys used.

To write the decryption code we observe the code and find out that the method of encryption is basically that the diagonal elements are of the form "k-x" where "k" are the "keys" generted for each character in the message and "x" is ASCII value of that character, this is because `-x % k = k - x` since keys are really big prime numbers so we just need to subtract the diagonals from the keys to get the required ASCII values and thus get the flag. This also means that there is a different key for each row i.e 36 keys.

To get the keys 

and thus the final code is
    
    from Crypto.Util.number import *

    def decrypt(encrypted_message: list, keys: list) -> str:
    x = len(encrypted_message)
    decrypted = ""
    
    for i in range(x):
        for j in range(x):
            if i == j:
                # Decrypt the character at the diagonal
                decrypted_char = ((-1) * encrypted_message[i][j]) % keys[i]
                decrypted += chr(decrypted_char)
                break
    
    return decrypted
    # Read the encrypted message from the file
    with open('out.txt', 'r') as f:
        encrypted_message = eval(f.read())
    # You need to have the original keys used for encryption
    keys = [579885124647369526157,476077290652714481873,349943003460314109673,525980091084766170491,438164697397128800629,525087896998708389373,485477731670335812503,435728240280813893887,540666002313690811639,584965747131027925409,439995449013303863551,418141579310939510821,460500404167421032201,361556514652689146477,328888527471701164673,479028008949338113297,445487775312973405009,342026121502245842533,503053158682598183707,387978067123272290321,476698436131566910073,413722495962750763163,493139132341670264171,573184381341628864837,372704451028203611159,539316115628053601867,434763088223071781417,466544168040450596147,459326708158581511673,589126675193834764871,531939900319278497203,329321060511978774469,384206381694376191809,455485400065236333571,465796268935821234409,365764966504311976627] 
   
    decrypted_message = decrypt(encrypted_message, keys)
    print("Decrypted message:", decrypted_message)

On running this code we get the flag.

Flag:
> *OASIS{Bro_Really_Modded_It_Negative}*

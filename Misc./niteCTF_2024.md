# niteCTF 2024

I participated in the niteCTF 2024, my team Cicada ranked 58 with 828 points, i scored 542 points and completed 5 challenges with 2 being OSINT, 2 being AI and 1 of Cryptography, this is a writeup of the 3 non OSINT challenges i solved

# La Casa de Papel

**Description:** Word on the street is Bob's about to make a big withdrawal. Too bad you're the one holding his ID. Can you charm Alice into making the transfer before she catches on?

We are given the code and a way to connect 
```
ncat --ssl la-casa-de-papel.chals.nitectf2024.live 1337
```
```
import hashlib
import base64
import pyfiglet

def secret():
    return "XXXXXXXXXXXXXXXXXXXXX"  # Length = 21

def md5(secret, msg):
    hash = hashlib.md5(secret + msg).hexdigest().encode()
    return base64.b64encode(hash).decode()

def menu(secret):
    while True:
        print("\n1. Practice Convo")
        print("2. Let's Fool Alice!")
        print("3. Crack the Vault")
        print("4. Exit")
        choice = input("Choose an option: ")
        if choice == '1':
            practice_convo(secret)
        elif choice == '2':
            fool_alice(secret)
        elif choice == '3':
            crack_the_vault()
        elif choice == '4':
            print("Exiting...")
            break
        else:
            print("Invalid choice. Please try again.")

def practice_convo(secret):
    message = input("Send a message: ")
    hash = md5(secret, message.encode('latin-1'))
    print(f"Here is your encrypted message: {hash}")

def fool_alice(secret):
    print("\nBot: Okay, let's see if you're the real deal. What's your name?")
    user_name = input("Your name: ").encode('latin-1')
    user_name = user_name.decode('unicode_escape').encode('latin-1')
    print("\nBot: Please provide your HMAC")
    user_hmac = input("Your HMAC: ").encode('latin-1')

    if b"Bob" in user_name:
        hash = base64.b64decode(md5(secret, user_name))
        if user_hmac == hash:
            print("\nAlice: Oh hey Bob! Here is the vault code you wanted:")
            with open('secret.txt', 'r') as file:
                secret_content = file.read()
                print(secret_content)
        else:
            print("\nAlice: LIARRRRRRR!!")
    else:
        print("\nAlice: IMPOSTERRRR")

def crack_the_vault():
    print("\nVault Person: Enter password")
    passs = input("Password: ")

    with open('secret.txt', 'r') as file:
        secret_content = file.read().strip()
        if passs == secret_content:
            with open('flag.txt', 'r') as flag_file:
                flag_content = flag_file.read().strip()
                print(f"\nVault Unlocked! The flag is: {flag_content}")
        else:
            print("Incorrect password!")

if __name__ == "__main__":
    secret_key = secret().encode()
    ascii_art = pyfiglet.figlet_format("La Casa de Papel")
    print(ascii_art)
    menu(secret_key)
```
So i started the challenge by understanding the code

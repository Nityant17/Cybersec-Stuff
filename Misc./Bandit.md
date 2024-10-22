# Bandit
Bandit is a wargame made for beginners to get them started on how to play wargames

## Level 0
We need to create a ssh link between the site and our terminal so we do that by entering `ssh bandit0@bandit.labs.overthewire.org -p 2220` where "bandit0" is the username, then its followed by the domain that we need to connect to and `-p` is used to connect to the specified port "2220" and finally it will ask for the password. 
> password: "bandit0" 

## Level 1
We need to read the "readme" file to get the password for the next level so we just use `cat readme` to do that. 
> password: "ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If"

## Level 2
We need to read the "-" file to get the password for next level so we do that by using `cat ./-` (we add "./" since "-" is a special character so it assumes its there to give an argument). 
> password: "263JGJPfgU6LtdEvgfWU1XP5yac29mFx"

## Level 3
We need to read the file "spaces in this filename" to get the flag, since we cant enter this file name directly in the command due to the space, I used the help of "Tab" key what i did was enter `cat spac` and clicked "Tab" it auto filled the command to read the only available file starting with "spac" and thus the command i finally got was `cat spaces\ in\ this\ filename` which worked and i got the password.
> password: "MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx"

## Level 4
We 
> password: ""

## Level 5
We 
> password: ""

## Level 6
We 
> password: ""

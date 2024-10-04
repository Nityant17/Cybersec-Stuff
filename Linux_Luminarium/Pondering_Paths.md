# Pondering Paths  
- Used the `ssh -i key hacker@pwn.college` command in the terminal to establish connection between the terminal and [pwn.college](https://pwn.college/)

## The Root
- Commands used: `/path/to/program`
- Thought Process: Need to run a program "pwn" so have to provide the path to the program.  
- Solution: Start the challenge, input the command `/pwn` to provide the absolute path to the program "pwn" and run the program.  
- Flag Obtained: pwn.college{wTJXuNWgdAtmNcWldhERWicO1lI.dhzN5QDLwMTN0czW} 

## Program and absolute paths
- Commands used: `/path/to/program`
- Thought Process: Need to run a program "run" so have to provide the path to the program.  
- Solution: Start the challenge, input the command `/challenge/run` to provide the absolute path to the program "run" and run the program.  
- Flag Obtained: pwn.college{8q0lSIhwUn4jHnAD_31630V3XBz.dVDN1QDLwMTN0czW} 

## Position thy self
- Commands used: `cd path`, `cd ..`, `/path/to/program`
- Thought Process: Need to run a program "run" so we provide the path to the program, it shows we need to be in "etc" directory so use `cd ..` and `cd path` to go into "etc" and then run the program again.    
- Solution: Start the challenge, use `cd ..` and `cd path` command to go into "etc" directory, input `/challenge/run` to provide the absolute path to the program "run" and run the program.  
- Flag Obtained: pwn.college{8VKb_2A6RrzhdOXbDnaJIEYiKKF.dZDN1QDLwMTN0czW} 

## Position elsewhere
- Commands used: `cd path`, `cd ..`, `/path/to/program`
- Thought Process: Need to run a program "run" so we provide the path to the program, it shows we need to be in "/var/log" directory so use `cd ..` and `cd path` to go into "/var/log" and then run the program again.  
- Solution: Start the challenge, use `cd ..` and `cd path` command to go into "/var/log" directory, input `/challenge/run` to provide the absolute path to the program "run" and run the program.  
- Flag Obtained: pwn.college{sq5gPhcSYO1IXoVXMgbA5bk37AU.ddDN1QDLwMTN0czW} 

## Position yet elsewhere
- Commands used:  `cd path`, `cd ..`, `/path/to/program`
- Thought Process: Need to run a program "run" so we provide the path to the program, it shows we need to be in "/usr/share/doc/fontconfig" directory so use `cd ..` and `cd path` to go into "/usr/share/doc/fontconfig" and then run the program again.  
- Solution: Start the challenge, use `cd ..` and `cd path` command to go into "/usr/share/doc/fontconfig" directory, input `/challenge/run` to provide the absolute path to the program "run" and run the program.  
- Flag Obtained: pwn.college{4mJoojKB4Gz206TM6miaVQ72bml.dhDN1QDLwMTN0czW} 

## Implicit relative paths, from /
- Commands used: `cd path`, `cd ..`, `relative/path`
- Thought Process: Need to run a program "run" so we provide the path to the program, it shows we need to provide a relative path from root directory so use `cd ..` and `cd path` to go into "/" and then input relative path to run the program again.  
- Solution: Start the challenge, use `cd ..` and `cd path` command to go into "/" directory, input `challenge/run` to provide the relative path to the program "run" and run the program.  
- Flag Obtained: pwn.college{cdmWFrVZpnLI6wUe9dYAsKKgZdo.dlDN1QDLwMTN0czW} 

## Explicit relative paths, from /
- Commands used:
- Thought Process:  
- Solution:  
- Flag Obtained: 

## Implicit relative path
- Commands used:
- Thought Process:  
- Solution:  
- Flag Obtained: 

## Home sweet Home
- Commands used:
- Thought Process:  
- Solution:  
- Flag Obtained: 

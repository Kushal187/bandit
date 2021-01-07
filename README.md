Bandit Writeup

#level 0-1
log into bandit0 using : ssh bandit0@bandit.labs.overthewire.org -p 2220
use ls to list the files
there is a file called readme
use cat to read it ( cat readme) and password obtained
pass:boJ9jbbUNNfktd78OOpsqOltutMc3MY1

#level 1-2
use ls 
you find - file
use cat <- to read file
pass : CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

#level 2-3
pass stored in file called "spaces in this filename"
use cat "spaces in this filename"
pass :UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK

#level 3-4
go to inhere directory using cd
use ls -a to display all files
command cat .hidden to obtain password
pass : pIwrPrtPN36QITSp3EQaw936yaFoFgAB

#level 4-5
use ls to show files
use find .-type f | xargs file
"|" is used to indicate two commands at once
xargs is used to show the file type
then open file with ascii.text
pass : koReBOKuIDDepwhWk7jZC0RTdopnAYKh

#level 5-6
ls to find all files
go to directory
use find -size 1033c! -executable
/maybehere07/.file2
use cd and cat to open and read .file2
pass: DXjZPULLxYr17uwoI01bNLQbtFemEgo7

#level 6-7
ls doesn't work
use find /-user bandit7 -group bandit6 -size 33c
c indicates bytes
we will get many permission denied messages 
find bandit7.password in it
go to the directory of bandit7.password and use cat to read it
pass: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs

#level 7-8
use ls to get data.txt
to find the word millionth use grep command
grep -w "millionth" data.txt
we use w for searching for word
And we get the password
pass: cvX2JJa4CFALtqS87jk27qwqGhBM9plV

#level 8-9
have to find line of text that occurs only once
first have to sort data.txt
then we use uniq -u command to remove all files that occur more than once
final command is : cat data.txt| sort |uniq -u
pass: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR

#level 9-10
use strings command on data.txt
once used it makes the filr contents readable
once you scroll up you can see === passowrd
command : strings data.txt
pass: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk

#level 10-11
base64 command is used to encode or decode text in a file
to decode we have to use " base64 --decode"
command is : cat data.txt | base64 --decode
pass: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR

#level 11-12
tr command is used to translate between characters
for example, it can transform lowercase to uppercase etc.
ROT13 is a type of encryption that translates the letters by 13 places
command : cat data.txt | tr "A-Za-z" "N-ZA-Mn-za-m"
pass : 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu

#level 12-13
We have to create a tmp directory and decompress the files till we get
the ascii text file
pass : 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL

#level 13-14
using ls we can find a file called sshkey.private
we have to log into bandit14 user
for this we have to use ssh -i command at localhost
i is for identity file
command : ssh -i sshkey.private bandit14@localhost
once in bandit14 we have to go to the directory /etc/bandit_pass using cd
use ls
we find bandit14
cat bandit14 and obtain password
pass : 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e

#level 14-15
have to use nc command to send files etc between ports
it can be used fot port redirection,port scanning etc.
can also be used to open remote connections
use : nc localhost 30000
then enter the password of level 14
this gives you output of password of 15
pass:BfMYroe26WYalil77FoDi9qh59eK5xNr

#level 15-16
we have to use openssl and s_client commands to connect to ssl
command: openssl s_client -connect localhost:30001
port specified is 30001
after connecting, enter the password for 15
output given is password for next level
pass: cluFn7wTiGryunymYOu4RcffSxQluehd

#level 16-17
first we have to check for open hosts using nmap command
nmap -p localhost
log into port 31790 using openssl s_client -connect localhost:31790
enter password of 16
after entering password of 16 we get an RSA key
copy the key 
create tmp directory
go to tmp directory and create file called sshkey.pvt using touch sshkey.pvt
to edit the file use nano sshkey.pvt
paste the rsa key and save and exit
now change permissions of sshkey.pvt using:
chmod 700 sshkey.pvt
now log onto bandit 17 using the sshkey
command: ssh -i sshkey.pvt bandit17@localhost
to obtain pass of 17 go to /etc/bandit_pass/bandit17
cat bandit17 to get its password
pass : xLYVMN9WE5zQ5vHacb0sZEVqbrp7nBTn

#level 17-18
have to use diff command to differntiate between the two files
use diff passwords.old passwords.new
you get two passwords
second password is the required one
pass: kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd

#level 18-19
we cannot access this level as when we try to login it disconnects immediately
so we should use cat while logging in to get the password stored in readme file
command: ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
pass: IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x

#level 19-20
have to run the file using ./bandit20-do
we get instructions
now password is stored in /etc/bandit_pass/bandit20
to obtain this we have to use the following command
./bandit20-do cat /etc/bandit_pass/bandit20
pass: GbKksEFF4yrVs6il55v6gwY5aVje5f0j

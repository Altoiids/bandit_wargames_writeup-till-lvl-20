# bandit_wargames_writeup-till-lvl-20
# Level - 0

## Commands Used
<pre>
ssh bandit0@bindit.labs.overthewire.org
</pre> 

## Flag
bandit0

# Level - 1

## Commands Used
<pre> 
ssh bandit1@bandit.labs.overthewire.org
ls -a #to list all the files
cat readme #  to see the content of file
exit
#Note : ssh and exit is common in all the levels we have to enter password received in previous level to enter next level.
</pre> 

## Flag
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

# Level - 2

## Commands Used
<pre>
ls -a #to list all the files
cat ./-#  to see the content of file
</pre> 

## Flag
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

# Level - 3

## Commands Used
<pre>
ls -a #to list all the files
cat "spaces in this filename" # to see the content of file
</pre> 

## Flag
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

# Level - 4

## Commands Used
<pre>
ls
cd inhere/
ls
ls -al
cat .hidden

</pre> 

## Flag
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe


# Level - 5

## Commands Used
<pre>
ls -a #to list all the files
cd inhere # to get into inhere directory
ls -a  #to list all the files
file ./* # to see the datatypes of all the files
cat ./-file07 #  to see the content of file
</pre> 

## Flag
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR



# Level - 6

## Commands Used
<pre>
ls -a #to list all the files
cd inhere # to get into inhere directory
ls -a  #to list all the files
find . -size 1033c # to find the file of this particular size,  there is only one file so this is our file.
cat ./maybehere07/.file2 #  to see the content of file
</pre> 

## Flag
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

# Level - 7

## Commands Used
<pre>
find / -user bandit7 -group bandit6 -size 33c -exec ls -la {} + # to find a file with user bandit 7 , group bandit 6 size 33c and ls -la to list it.the last file satifies all these. for all other file permission is denied.
cat /var/lib/dpkg/info/bandit7.password
</pre> 

## Flag
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

# Level - 8

## Commands Used
<pre>
ls -la # to list all the commands
cat data.txt | grep millionth #it will print the text of the the line after the word millionth
</pre> 

## Flag
TESKZC0XvTetK0S9xNwm25STk5iWrBvP

# Level - 9

## Commands Used
<pre>
cat data.txt| uniq -u #uniq helps us to print unique thereby printing the string
</pre>
## Flag
EN632PlfYiZbn3PhVK3XOGSlNInNE00t

# Level - 10

## Commands Used
<pre>
ls
cat data.txt | grep = # it will print line after this pattern 
</pre> 

## Flag
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s

# Level - 11

## Commands Used
<pre>
ls
cat data.txt | base64 —decode #it will decode the text in the file using decode64 technique and the content will be flag
</pre> 

## Flag
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM


# Level - 12

## Commands Used
<pre>

ls 
cat data.txt|tr 'A-Za-z' 'N-ZA-Mn-za-m' #data.txt present the alphabats have been shifted by 13 positions so we used the command tr to again apply rot 13(rotating alphabats again by 13 positions)

</pre> 

## Flag
JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

# Level - 13

## Commands Used
<pre>
ls #show data.txt file
#if we try to do xxd -r on data.txt file directly permission is being denied.so we do as mentioned
mkdir /tmp/exper  # makes new directory
cp data.txt /tmp/exper
cd /tmp/exper
ls #shows data.txt file
#if we cat it is in form of hexdump so we apply to convert to binary form
xxd -r data.txt > data1
file data1
zcat data1 > data2
file data2
bzcat data2 > data3
file data3
zcat data3 > data4
file data4
tar -xvf data4
file data5.bin
tar -xvf data5.bin
file data6.bin
bzcat data6.bin > data7
file data7
tar -xvf data7
file data8.bin
zcat data8.bin > data9
file data9
cat data9
#we apply a series of decompressions based on compression type bzcat for bzip2 compression
#zcat for gzip compression
#tar -xvf for  extracting POSIX tar archive file.  f for file x for extraction
</pre> 

## Flag
wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw


# Level - 14

## Commands Used
<pre>
ssh -i sshkey.private bandit14@localhost -p2220. #we logged in as user bandit14 on localhost(bandit13) using private ssh key 
ls /etc/bandit_pass/bandit14
cat /etc/bandit_pass/bandit14
</pre> 

## Flag
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq


# Level - 15

## Commands Used
<pre>
nc localhost 30000 #nc command to connect to different server using diff port number on our localhost
#then submitted previous password and we recieved
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
</pre> 

## Flag
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

# Level - 16

## Commands Used
<pre>
openssl s_client localhost:30001. # s_client option  for making remote connection using ssl/tls s_server for making from server side
</pre> 

## Flag
JQttfApK4SeyHwDlI9SXGR50qclOAil1


# Level - 17

## Commands Used
<pre>
netstat -aon  # “a” represents all connections and ports, “o” represents the owning process ID, and “n” represents the addresses and port numbers as numerals.it gave portnumbers with listening and tcp connection tried different ports and finally got it.
openssl s_client localhost:31790 #it gave ssh private key use it to login to next level
chmod 600 /tmp/private17.key #to modify permissions
nano /tmp/private17.key #to add private rsa key
ssh bandit17@localhost -i /tmp/private17.key -p 2220 # to login to next level


</pre> 

## Flag





# Level - 18

## Commands Used
<pre>
diff passwords.old passwords.new #did as directed
</pre> 

## Flag
hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg



# Level - 19

## Commands Used
<pre>
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme #by doing this cat will be executed before we logout so we will get the password.
</pre> 

## Flag
awhqfNnAbc1naukrpqDYcF95h7HoMTrC


# Level - 20

## Commands Used
<pre>
./bandit20-do cat /etc/bandit\_pass/bandit20 #did as directed
</pre> 

## Flag
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM






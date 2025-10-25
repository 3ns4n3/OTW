- **Level 0**
	cat

- **Level 1**
	dashed filename cat ./- to get flag
- **Level 2**
	spaces in the file name.... I did ./ (tab completion and it worked fine)
- **Level 3**
	hidden file. ls -a to get flag in the "inhere directory"
- **Level 4**
	"find the only human readable file.. "  
	- ran command file ./-* | grep 'ASCII'
- **Level 5
- Command: 
- find /path/to/inhere -type f -size 1033c -not -executable -exec file {} + | grep 'text'

- **Level 6
- The password for the next level is stored **somewhere on the server** and has all of the following properties:
	- owned by user bandit7
	- owned by group bandit6
	- 33 bytes in size
	- find -size b '33'
	- -user bandit7
	- -group bandit6
	- the command is: **find /. -size 33c -user bandit7 -group bandit6 2>/dev/null** 
- **Level 7**
	-The password for the next level is stored in the file data.txt next to the word millionth
	- Ez grep command: 
	-  cat data.txt| sort | grep 'millionth
- **Level 8**
	The password for the next level is stored in the file data.txt and is the only line of text that occurs only once
	-sort data.txt | uniq -u
- **Level 9**
	- The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
	- Got lucky on this one ran the command it was sitting a bit higher in the terminal  **sort -h data.txt**
- **Level 10**
	-decode some base64 ez 
- **Level 11**
	-decode some rot13
- **Level 12**
		had to make do dir to work on files.. made it under /tmo
		1. xxd -r to revert hexdump
		2. file reverthex.txt shows gzip compressed
		3. had to change to everthext.txt to .gz
		4. gzip -d revertedhext.gz
		5. file revertedhex shows bzip now
		6. bzip2 -d leaves us with betterdata.out
		7. betterdata.out is a gzipfile
		8. file that shows its a POSIX tar archive
		9. tar -xvf is now data5.bin
		10. tar -xvf is now data6.bin which is a bzip2 file
		11. now its a tar file again
		12. which is now a gzip file
		13. holy shit we are done.
- **Level 13**
	found key, copied and pasted to my box and saved in a file. 
	 1. had to chmod 600 the file in order to get proper permissions for ssh
	 2. ssh -i keyname 
- **Level 14**
	- cat /etc/bandit_pass/bandit14 
	- MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
- **Level 15**
- I dont remember what this was.. think just a netcat listener
- **Level 16**
  + submit password of 15 over ssl to port 3001
  + used follow command openssl s_client -connect localhost:30001
  + then it waited for me to paste the flag
- **Level 17**
  + scan for open ports on local host
  + nmap -p 31000-32000
  + 5 came back as up
  + reran nmap -script ssl-enum-ciphers and rest of previous command 2 came back with cipers
  + run openssl s_client -quiet -connect localhost:port otherwise it wont work for this one..
  + responded with a private key.
- **Level 18**
  + ssh -i bandit17key bandit17@bandit.labs.overthewire.org -p 2220
 + diff file1 and file 2
- **Level 19**
   + ssh bandit18@bandit.labs.overthewire.org -p 2220 bash --noprofile
   + this one had a .bashrc file that was modifed to log you out automatically. ran with no profile allowed you to work around that. perhaps -norc would work as well
- **Level 20**
	+ familirization with setuid binary
 	+ ran /bandit20-do cat /etc/bandit_pass/bandit20 to get pass
- **Level 21**
	+ had to run setuid binay to figure what it did
 + echo old password into a nc listener and put it in the background
- **Level22**
+ check cronjobs.. see script. Cat script profit$$
- **Level 23**
+ find script read it... run part of the script use that for your target
- **Level 24**
  + we must first make a temp dir
  + mktmp -d
  + cd there and make script
  + set permissions to max so you can you run script
  + make empty password file to have cronjob append
  + cp script from tmp to target dir
  + script : cat /etc/bandit_pass/bandit24 > /tmp/tmp.QeNPZVkecn/password
  + #!/bin/bash
for i in {0000..9999}
do 
	echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i" >> response.txt

done

cat response.txt | nc localhost 30002 > results.txt

- **Level 25**
  + We need to determine the shell that bandit26 ueses
  + cat /etc/passwd/ and grep bandit26 to see it is using the /usr/bin/showtext shell...
  + lets read that.. its written in #!/bin/sh and is using  more ~/text.txt
  + this one has to be logged into with a TINY terminal so MORE wont be displayed all the way, when logged in use -v to get into vim
  + now we can use vim do some things we want
  + :shell will set us in the defualt shell :set shell /bin/bash will put us in bash
  + use the setgid script to read /etc/bandit_pass/bandit27
- **Level 27**
	+ need to git over ssh it seems
	+ to do this we have to modify the ssh config file under ~/.ssh/config
	+ I didnt have one so I made one. inside I needed to specify the host and port
	+ Host bandit.labs.overthewire.org
		Port 2220
		Host *
		Port 2220
	+ ran git clone ssh://bandit27-git@bandit.labs.overthewire.org/home/bandit27-git/repo and had no problems
- **Level 28**

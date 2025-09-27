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

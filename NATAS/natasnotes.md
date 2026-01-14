**Natas 0**
  + view source
  + 0nzCigAq7t2iALyvU9xcHlYN4MlkIwlq
**Natas 1**
  + ctl+shift+k
  + hit inspector and looked in the index
  + TguMNxKo1DSa1tujBLuZJnDUlCcUAPlI
**Natas 2**
+ view source
+ notice /files.png
+ http://natas2.natas.labs.overthewire.org/files/users.txt
+ alice:BYNdCesZqW
```
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:3gqisGdR0pjm6tpkDKdIWO2hSvchLeYH
eve:zo4mJWyNj2
mallory:9urtcpzBmH
```
**Natas 3**
+ "no more information, not even google will find"
+ robots.txt shows  a /s3cr3ct/ which shows natas4:QryZXc2e0zahULdHrtHxzyYkj59kUxLQ

**Natas 4**
Access disallowed. You are visiting from "http://natas4.natas.labs.overthewire.org/" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/" 

+ must look at referer. f12 right click index.php, copy value as curl
+ change this line: -H 'Referer: http://natas5.natas.labs.overthewire.org/'
+ refers as natas5... profit
**Natas 5**0n35PkggAPm2zbEpOU802c0x0Msn1ToK
+ this one relates to cookies... check out the storage tab and look at cookies, see a logged in value of 0 and make it 1...
**Natas 6**
+ Access granted. The password for natas6 is 0RoJwHdSKWFTYR5WuiAewauSuNaBXned
+ view page source shows php includes /secret.inc
+ under network see a file.. view page source = FOEIUWGHFEEUHOFUOIU
+ **Natas 7**
+  The password for natas7 is bmg8SvU1LizuWjx3y7xkNERkHxGre0GS
+  
<!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->
+ path traversal = ```http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8```
**Natas 8**  xcoXLmzMkoIP9D7hlgPlh9XD7OgLAe5Q
  + page source showed the procces in which it was encoded..
**Natas 9**
  + The password for natas9 is ZE1ck82lmdGIoErlhQgWND6j2Wzz6b6t 

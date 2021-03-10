https://overthewire.org/wargames/bandit/

<h1>level0:</h1>

as the level0 said i ssh-ed to the server: 
```
ssh 'bandit0'@bandit.labs.overthewire.org -p 2220
```
pass: bandit0

and there i searched for files

```
ls -la
cat readme
```
in the readme file the bandit1 password was found
so i exited to connect to level1 
```
exit
```
<h1>level1:</h1>

```
ssh 'bandit1'@bandit.labs.overthewire.org -p 222
```
pass: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

there seems to be a file thats named -
after googling it i found out that to read it i had to use
```
cat ./-
```

<h1>level2:</h1>

```
ssh 'bandit2'@bandit.labs.overthewire.org -p 222
```
pass: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

theres a file with spaces in its name
```
cat 'spaces in this filename'
```

<h1>level3:</h1>

```
ssh 'bandit3'@bandit.labs.overthewire.org -p 222
```
pass: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
cat ./inhere/.hidden
```

<h1>level4:</h1>

```
ssh 'bandit4'@bandit.labs.overthewire.org -p 222
```
pass: pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
file ./-file0*
cat ./inhere/-file07
```
fisrtly i had to know which is human-readable > ASCII and then read it


<h1>level5:</h1>

```
ssh 'bandit5'@bandit.labs.overthewire.org -p 222
```
pass: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```
find ./inhere/ -size 1033c
cat ./inhere/maybehere07/.file2
```
the size was given so i searched by that and found that .file2 had the criteria 

<h1>level6:</h1>

```
ssh 'bandit6'@bandit.labs.overthewire.org -p 222
```
pass: DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```
find / -user bandit7 -group bandit6 -size 33c
cat /var/lib/dpkg/info/bandit7.password
```
based on the criteria finded the file path and catted it


<h1>level7:</h1>

```
ssh 'bandit7'@bandit.labs.overthewire.org -p 222
```
pass: HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs
```
cat data.txt | grep "millionth"
```


<h1>level8:</h1>

```
ssh 'bandit8'@bandit.labs.overthewire.org -p 222
```
pass: cvX2JJa4CFALtqS87jk27qwqGhBM9plV
```
cat data.txt | sort | uniq -u
```
to get the none repetitive lines


<h1>level9:</h1>

```
ssh 'bandit9'@bandit.labs.overthewire.org -p 222
```
pass: UsvVyFSfZZWbi6wgC7dAFyFuR6jQQUhR
```
strings data.txt | grep -E '=+'
```
to get the regex of = many times


<h1>level10:</h1>

```
ssh 'bandit10'@bandit.labs.overthewire.org -p 222
```
pass: truKLdjsbJ5g7yyJ2X2R0o3a5HQJFuLk
```
cat data.txt | base64 --d
```

<h1>level11:</h1>

```
ssh 'bandit11'@bandit.labs.overthewire.org -p 222
```
pass: IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
```
cat data.txt  | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
```
to decode ROT13


<h1>level12:</h1>

```
ssh 'bandit12'@bandit.labs.overthewire.org -p 222
```
pass: 5Te8Y4drgCRfCx8ugdwuEX8KFC6k2EUu
```
mkdir /tmp/banditooo
cp data.txt /tmp/banditooo
xxd -r data.txt tmp
file tmp 
mv tmp tmp.gz
gzip -d tmp.gz
file tmp
mv tmp tmp.bz2
bzip2 -d tmp.bz2
file tmp
mv tmp tmp.gz
gzip -d tmp.gz 
file tmp 
tar xvf tmp
tar xvf data5.bin
file data6.bin
mv data6.bin data6.bz2
bzip2 -d data6.bz2
file data6
tar xvf data6
mv data8.bin data8.gz
gzip -d data8
file data8
cat data8
```

<h1>level13:</h1>

```
ssh 'bandit13'@bandit.labs.overthewire.org -p 222
```
pass: 8ZjyCRiBWFYkneahHwxCv3wb2a1ORpYL
```
cat /etc/bandit_pass/bandit14
ssh -i sshkey.private bandit14@localhost
cat /etc/bandit_pass/bandit14
```
catting permission denied so i had to be bandit14
**NOTE:** do not exit connection yet!

<h1>level14:</h1>

```
echo 4wcYUJFw0k0XLShlDzztnTBHiqxU3b3e | nc localhost 30000
```
while still in the bandit13 connection we got the bandit 15 pass by echoing the previous pass 


<h1>level15:</h1>

while still in the same pervious connection 

pass: BfMYroe26WYalil77FoDi9qh59eK5xNr
```
echo BfMYroe26WYalil77FoDi9qh59eK5xNr | openssl s_client -ign_eof -connect localhost:30001
```


<h1>level16:</h1>

```
ssh 'bandit16'@bandit.labs.overthewire.org -p 222
```
pass: cluFn7wTiGryunymYOu4RcffSxQluehd
```
nmap 127.0.0.1 -p 31000-32000
echo cluFn7wTiGryunymYOu4RcffSxQluehd | openssl s_client -ign_eof -connect localhost:31790
```
we fist had to scan the port range and then try each open port for the above line, ended up being port 31790 that gives us the next pass, which was a ssh key.

<h1>level17:</h1>
 
 using the ssh key we copied it into a file
```
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----
```
via
```
nano ssh 
sudo ssh -i ssh 'bandit17'@bandit.labs.overthewire.org -p 2220
comm <(sort passwords.new) <(sort passwords.old) -23
```

<h1>level18:</h1>

```
sudo ssh -t 'bandit18'@bandit.labs.overthewire.org -p 2220 /bin/sh
```
pass: kfBf3eYk5BPBRzwjqutbbfE887SVc5Yd
```
ls
cat readme
```

<h1>level19:</h1>

```
ssh 'bandit19'@bandit.labs.overthewire.org -p 222
```
pass: IueksS7Ubh8G3DCwVzrTd8rAVOwq3M5x
```
ls -la bandit20-do
file bandit20-do
./bandit20-do id
./bandit20-do cat /etc/bandit_pass/bandit20
```
used the permissions of bandit20-do to read /etc/bandit_pass/bandit20


<h1>level20:</h1>

```
ssh 'bandit20'@bandit.labs.overthewire.org -p 222
```
pass: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
```

```













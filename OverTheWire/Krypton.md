https://overthewire.org/wargames/krypton/

<h1>level0:</h1>

using [cybechef](https://gchq.github.io/CyberChef/) i decoded it by base64
```
S1JZUFRPTklTR1JFQVQ=
```
gave the password
```
KRYPTONISGREAT
```
then connect via ssh
```
ssh krypton1@krypton.labs.overthewire.org -p 2231 
cd ..
cd ../../krypton/krypton1
cat krypton2 
```
output
```
YRIRY GJB CNFFJBEQ EBGGRA
```
so i used [caesar cipher](https://www.dcode.fr/caesar-cipher) and turned out rot13
```
LEVEL TWO PASSWORD ROTTEN
```

<h1>level1:</h1>

```
ssh krypton2@krypton.labs.overthewire.org -p 2231 
```
pass: ROTTEN
```
cd ../../krypton/krypton2
cat krypton3 
```
output
```
OMQEMDUEQMEK
```
i used [caesar cipher](https://www.dcode.fr/caesar-cipher) 
```
CAESARISEASY
```

<h1>level2:</h1>

```
ssh krypton3@krypton.labs.overthewire.org -p 2231 
```
pass: CAESARISEASY

copied found1, found2, found3 and krypton4 and submitted it toghther because krypton4 alone isnt giving an answer in [quipquip](https://quipqiup.com/), also [ref](ref: https://programmercave0.github.io/blog/2020/01/07/Krypton-Level-3-to-Level-5-Basic-Cryptographic-Techniques)

output
```
well done the level four password is brute 
```


<h1>level3:</h1>

```
ssh krypton4@krypton.labs.overthewire.org -p 2231 
```
pass: BRUTE
```
cd ../../krypton/krypton4
```
copied found1 and found2 with key length 6 (its was a hint) in [vigenere cipher](https://www.dcode.fr/vigenere-cipher) 
which gave the key "FREKEY" then used it to decode krypton4  
```
CLEAR TEXT
```

<h1>level4:</h1>

```
ssh krypton5@krypton.labs.overthewire.org -p 2231 
```
pass: CLEARTEXT

```
cd ../../krypton/krypton5
```
copied found1, found2 and found3 in [vigenere cipher](https://www.dcode.fr/vigenere-cipher) that gave the key/password "KEYLENGTH" that i used for decoding it again in vigenere cipher
```
RANDO M
```










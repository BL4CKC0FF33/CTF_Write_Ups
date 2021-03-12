https://play.picoctf.org/practice


<h1>challenge86 - 2Warm</h1> 
https://play.picoctf.org/practice/challenge/86

i got the flag [via](http://www.unitconversion.org/numbers/base-10-to-binary-conversion.html) changing decimal to binary: 
```
picoCTF{101010}
```

<h1>challenge58 - Warmed Up</h1> 
https://play.picoctf.org/practice/challenge/58

i got the flag [via](https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=0x3D) changing hex to decimal: 
```
picoCTF{61}
```

<h1>challenge22 - Lets Warm Up</h1> 
https://play.picoctf.org/practice/challenge/22

i got the flag [via](https://www.rapidtables.com/convert/number/hex-to-ascii.html) changing hex to ASCII: 
```
picoCTF{p}
```

<h1>challenge37 - strings it</h1> 
https://play.picoctf.org/practice/challenge/37

i got the flag via downloading the file and strings it: 
```
wget https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings
strings strings  | grep picoCTF
```
gave the flag:
```
picoCTF{5tRIng5_1T_d66c7bb7}
```

<h1>challenge67 - Bases</h1> 
https://play.picoctf.org/practice/challenge/67

i got the flag via decoding the given string from base64: 
```
echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
```
gave the flag:
```
picoCTF{l3arn_th3_r0p35}
```

<h1>challenge85 - First Grep</h1> 
https://play.picoctf.org/practice/challenge/85

i got the flag via catting then grepping the file: 
```
wget https://jupiter.challenges.picoctf.org/static/315d3325dc668ab7f1af9194f2de7e7a/file
cat file | grep picoCTF
```
gave the flag:
```
picoCTF{grep_is_good_to_find_things_f77e0797}
```

<h1>challenge34 - what's a net cat?</h1> 
https://play.picoctf.org/practice/challenge/34

i got the flag via connecting netcat to the given server and port: 
```
nc jupiter.challenges.picoctf.org 25103
```
gave the flag:
```
picoCTF{nEtCat_Mast3ry_d0c64587}
```

<h1>challenge48 - plumbing</h1> 
https://play.picoctf.org/practice/challenge/48

i got the flag via connecting netcat to the given server and port and outputting all of the output in a file: 
```
nc jupiter.challenges.picoctf.org 14291 >> output.txt
cat output.txt | grep picoCTF
```
gave the flag:
```
picoCTF{digital_plumb3r_ea8bfec7}
```

<h1>challenge49 - flag_shop</h1> 
https://play.picoctf.org/practice/challenge/49

i got the flag via connecting netcat and then i had to buy A HUGE amount to make it negative: 
```
nc jupiter.challenges.picoctf.org 44566
2
1
213213123
2
2
1
```
gave the flag:
```
picoCTF{m0n3y_bag5_68d16363}
```

<h1>challenge15 - mus1c</h1> 
https://play.picoctf.org/practice/challenge/15

i got the flag via copying the file and pasting it to [here](https://codewithrockstar.com/online) and then changing from [decimal to ASCII](https://www.rapidtables.com/convert/number/ascii-hex-bin-dec-converter.html) : 
```
wget https://jupiter.challenges.picoctf.org/static/c0863a3b0170d6dd176be3a595b4b75e/lyrics.txt
cat lyrics.txt
```
gave the flag:
```
picoCTF{rrrocknrn0113r}
```





























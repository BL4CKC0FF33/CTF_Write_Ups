https://play.picoctf.org/practice


<h1>challenge86</h1> 
https://play.picoctf.org/practice/challenge/86

i got the flag [via](http://www.unitconversion.org/numbers/base-10-to-binary-conversion.html) changing decimal to binary: 
```
picoCTF{101010}
```

<h1>challenge58</h1> 
https://play.picoctf.org/practice/challenge/58

i got the flag [via](https://www.rapidtables.com/convert/number/hex-to-decimal.html?x=0x3D) changing hex to decimal: 
```
picoCTF{61}
```

<h1>challenge22</h1> 
https://play.picoctf.org/practice/challenge/22

i got the flag [via](https://www.rapidtables.com/convert/number/hex-to-ascii.html) changing hex to ASCII: 
```
picoCTF{p}
```

<h1>challenge37</h1> 
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

<h1>challenge67</h1> 
https://play.picoctf.org/practice/challenge/67

i got the flag via decoding the given string from base64: 
```
echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
```
gave the flag:
```
picoCTF{l3arn_th3_r0p35}
```

<h1>challenge85</h1> 
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

<h1>challenge34</h1> 
https://play.picoctf.org/practice/challenge/34

i got the flag via connecting netcat to the given server and port: 
```
nc jupiter.challenges.picoctf.org 25103
```
gave the flag:
```
picoCTF{nEtCat_Mast3ry_d0c64587}
```

<h1>challenge48</h1> 
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



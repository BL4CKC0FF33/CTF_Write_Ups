https://ctf.nahamcon.com/

<h1>Challenge - Read The Rules</h1>
 
![1](https://user-images.githubusercontent.com/69141453/111119086-08626780-8540-11eb-9bdd-72f3cbd91751.png)

i went to the linked page and ***inspect page*** you'll find a comment there with 

```
flag{90bc54705794a62015369fd8e86e557b} 
```

<h1>Challenge - Buzz</h1>

![2](https://user-images.githubusercontent.com/69141453/111119396-77d85700-8540-11eb-95b0-4b226b6e7562.png)

after getting the file turned out that it was a zip file and then i had to change the extention and unzip it
```
wget https://ctf.nahamcon.com/files/1b9cf40e00b9f77f26f23bbe62aa5780/buzz?token=eyJ1c2VyX2lkIjo2MDI5LCJ0ZWFtX2lkIjpudWxsLCJmaWxlX2lkIjo0fQ.YE0CVA.FnaoH6yRW8oBNTiPRl4Aja-j44E
file buzz
mv buzz buzz.z
uncompress buzz.z
file buzz
strings buzz
```

<h1>Challenge - Shoelaces</h1>

![6](https://user-images.githubusercontent.com/69141453/111119647-c1c13d00-8540-11eb-8684-3823d6fb16e8.png)

at first i thought thete might be hidden files so i ran binwalk but it turned out its not that complex
```
strings  shoelaces.jpeg | grep flag
```
```
flag{137288e960a3ae9b148e8a7db16a69b0}
```

<h1>Challenge - Pollex</h1>

![7](https://user-images.githubusercontent.com/69141453/111119926-1bc20280-8541-11eb-8931-c48016359ea6.png)

there was hidden files so i extracted them and them checked them out, an image had the flag
```
binwalk --dd=".*" pollex
cd /_pollex.extracted
eog 14E
```
![77](https://user-images.githubusercontent.com/69141453/111120050-46ac5680-8541-11eb-8075-2caa51c65787.png)
```
flag{65c34a1ec121a286600ddd48fe36bc00}
```

<h1>Challenge - #NahamCon2021</h1>

![4](https://user-images.githubusercontent.com/69141453/111120256-8115f380-8541-11eb-8c94-889b3537059b.png)

i googled this and game me the flag:
```
#NahamCon2021 flag
```
![44](https://user-images.githubusercontent.com/69141453/111120278-87a46b00-8541-11eb-8d47-e787633955b5.png)


<h1>Challenge - Merch Store</h1>

![55](https://user-images.githubusercontent.com/69141453/111120523-d18d5100-8541-11eb-98b8-0483579b56fe.png)

going to the linked page and inspecting the pages until i found out that when i click on an item on the shop the flag shows as a comment

![5](https://user-images.githubusercontent.com/69141453/111120601-eec21f80-8541-11eb-8525-e8244bb4ffa5.png)



<h1>Challenge - esab64</h1>

![4](https://user-images.githubusercontent.com/69141453/111120907-58422e00-8542-11eb-9b01-92192e88a12c.png)

i googled ***was it a car or a cat i saw?*** and found the answer is that palindrome, reading from left-to-right is the same as right-to-left, but i was confused because decoding it from base64 wasnt working.
so i thought maybe [reverse](https://codebeautify.org/reverse-string) the string first then try to [decode](https://www.base64decode.org/) it. and that worked.

![44](https://user-images.githubusercontent.com/69141453/111121168-b1aa5d00-8542-11eb-96fc-f47d2174fcc1.png)
![444](https://user-images.githubusercontent.com/69141453/111121248-c981e100-8542-11eb-8228-984bd98cbbaa.png)
![4444](https://user-images.githubusercontent.com/69141453/111121275-d272b280-8542-11eb-8d1e-f93dc28f71de.png)


<h1>Challenge - Veebee</h1>

![8](https://user-images.githubusercontent.com/69141453/111136749-6ef18080-8554-11eb-8dc7-f358f0839337.png)

using johnHammond's [vbe-decoder](https://github.com/JohnHammond/vbe-decoder/blob/master/vbe-decoder.py) gave the flag
```
python3 decode-vbe.py veebee.vbe 
```
```
flag{f805593d933f5433f2a04f082f400d8c}
```

<h1>Challenge - Car Keys</h1>

![9](https://user-images.githubusercontent.com/69141453/111136867-8df01280-8554-11eb-9516-bac29e92e686.png)

its not a direct ceasar cipher, first you have to decypher it via keyed-ceasar then normal ceasar

![99](https://user-images.githubusercontent.com/69141453/111136950-a2340f80-8554-11eb-9ad7-cdd1af184008.png)
![999](https://user-images.githubusercontent.com/69141453/111136979-aa8c4a80-8554-11eb-8897-67f1f6c9a049.png)

















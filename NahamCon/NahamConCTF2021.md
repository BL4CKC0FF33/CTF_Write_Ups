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

```
flag{6f980c0101c8aa361977cac06508a3de}
```

<h1>Challenge - Eighth Circle</h1>

![1](https://user-images.githubusercontent.com/69141453/111176394-ae819200-857f-11eb-9900-79f35163d4ed.png)

at first i googled it and i got hellish stuff xD then i got a hint about [malbolge](https://malbolge.doleczek.pl/) to decode:
```
D'`r#LK\[}{{EUUTet,r*qo'nmlk5ihVB0S!>w<<)9xqYonsrqj0hPlkdcb(`Hd]#a`_A@VzZY;Qu8NMRQJn1MLKJCg*)ED=a$:?>7[;:981w/4-,P*p(L,%*)"!~}CB"!~}_uzs9wpotsrqj0Qmfkdcba'H^]\[Z~^W?[TSRWPt7MLKo2NMFj-IHG@dD&<;@?>76Z{9276/.R21q/.-&J*j(!E%$d"y?`_{ts9qpon4lTjohg-eMihg`&^cb[!_X@VzZ<RWVOTSLpP2HMFEDhBAFE>=BA:^8=6;:981Uvu-,10/(Lm%*)(!~D1 
```
```
flag{bf201f669b8c4adf8b91f09165ec8c5c}
```

<h1>Challenge - Chicken Wings</h1>

![7](https://user-images.githubusercontent.com/69141453/111180183-269d8700-8583-11eb-98eb-64b59ce4cd09.png)

i had no idea what to do with the output of catting the file, so i googled it and found an online website to decode it

![77](https://user-images.githubusercontent.com/69141453/111180408-65cbd800-8583-11eb-9edb-fbf0cd68aa45.png)
![777](https://user-images.githubusercontent.com/69141453/111180349-577dbc00-8583-11eb-8f87-f07941395205.png)


<h1>Challenge - The Mission</h1>

![3](https://user-images.githubusercontent.com/69141453/111176961-2d76ca80-8580-11eb-8227-5523d660e3de.png)

after visiting the linked page all i did was ***inspect page*** and found the flag in the comments


<h1>Challenge - Meet The Team</h1>

![2](https://user-images.githubusercontent.com/69141453/111177211-6616a400-8580-11eb-9d14-0f12a5b80f5c.png)

as for this challenge it says meet the team but the page doesnt display team members due to security but there was a github link in the page, and in that link i got the github repo by gitdump 

![22222](https://user-images.githubusercontent.com/69141453/111178643-be9a7100-8581-11eb-8e2e-c32bf2e9f1c8.png)
![22](https://user-images.githubusercontent.com/69141453/111178074-2f8d5900-8581-11eb-8d06-b3effb8c436c.png)

```
./GitTools/Dumper/gitdumper.sh http://constellations.page/.git/ git
cd git/.git
git show
```
```
flag{4063962f3a52f923ddb4411c139dd24c}
```

<h1>Challenge - Bionic</h1>

![6](https://user-images.githubusercontent.com/69141453/111179941-eccc8080-8582-11eb-840e-6c4f62426eb0.png)

i went to the linked page but nothing was unusual so i tried /robots.txt which worked and found the flag

![66](https://user-images.githubusercontent.com/69141453/111180655-9f044800-8583-11eb-8673-4799b5f88bce.png)



<h1>Challenge - Gus</h1>

![3](https://user-images.githubusercontent.com/69141453/111177735-e76e3680-8580-11eb-81d2-1ee0951809d8.png)

i had to dig the github since its a team member, then checked the commits one by one until i found a flag

![222](https://user-images.githubusercontent.com/69141453/111178153-403dcf00-8581-11eb-84e0-21e90f300ed0.png)
![2222](https://user-images.githubusercontent.com/69141453/111178200-4a5fcd80-8581-11eb-8e0e-0d32a8cea28c.png)

```
flag{84d5cc7e162895fa0a5834f1efdd0b32}
```


<h1>Challenge - Hercules</h1>

![4](https://user-images.githubusercontent.com/69141453/111178402-7d09c600-8581-11eb-9ee7-887a451a143e.png)

i checked the followers of gus and found someone named Hercules

![44](https://user-images.githubusercontent.com/69141453/111178494-97dc3a80-8581-11eb-9850-2fcc42bc1776.png)

i checked his commits and got the flag

![444](https://user-images.githubusercontent.com/69141453/111178532-a591c000-8581-11eb-81aa-26f8821d93e7.png)
![4444](https://user-images.githubusercontent.com/69141453/111178585-b2aeaf00-8581-11eb-9c88-8e78f6603d4b.png)


<h1>Challenge - Lyra</h1>

![5](https://user-images.githubusercontent.com/69141453/111178712-cce88d00-8581-11eb-95ba-28c345bf5bbd.png)

lyra's full name was in the git file
```
git show
```

![5555](https://user-images.githubusercontent.com/69141453/111178795-de319980-8581-11eb-9c06-f49ef8c208d8.png)

after that googled her name lyra patte with constellations and found her twitter account with this post 

![555](https://user-images.githubusercontent.com/69141453/111179043-12a55580-8582-11eb-9e97-5843eb5f6370.png)

which led to this page but i had to enumerate to folder 5 to find the flag

![55](https://user-images.githubusercontent.com/69141453/111179246-408a9a00-8582-11eb-8e20-6068e8a89cbe.png)










![8](https://user-images.githubusercontent.com/69141453/111179538-8e9f9d80-8582-11eb-95de-0c43acdea5b0.png)
![9](https://user-images.githubusercontent.com/69141453/111179546-8fd0ca80-8582-11eb-9a80-c10c0070cb90.png)
![10](https://user-images.githubusercontent.com/69141453/111179553-919a8e00-8582-11eb-8e2f-27165c7d4a25.png)
![1](https://user-images.githubusercontent.com/69141453/111179594-9bbc8c80-8582-11eb-9096-db502d18a5aa.png)
![2](https://user-images.githubusercontent.com/69141453/111179598-9cedb980-8582-11eb-9d7c-d3a0ef5dda97.png)
![3](https://user-images.githubusercontent.com/69141453/111179602-9e1ee680-8582-11eb-847d-a37dfb1f383c.png)
![55](https://user-images.githubusercontent.com/69141453/111179726-babb1e80-8582-11eb-959f-57e886a73c24.png)
![55](https://user-images.githubusercontent.com/69141453/111180286-45038280-8583-11eb-8bdc-ea871378e949.png)


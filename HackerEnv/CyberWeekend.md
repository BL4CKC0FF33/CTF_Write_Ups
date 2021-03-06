![1](https://user-images.githubusercontent.com/69141453/110219996-899e6800-7e77-11eb-9e61-95b4a7ed387a.PNG)
```
10.0.100.3
``` 
 as the text in the webpage said, i inspected the source code via **rightclick > inspect code** and i found an instruction saying "decode b64" so i opened an [online base64 decoder](https://www.base64decode.org/) and decoded the message

![2](https://user-images.githubusercontent.com/69141453/110220023-c702f580-7e77-11eb-8862-033836a37dc6.PNG)

then i went to the path **/robots.txt** and found 2 paths

![3](https://user-images.githubusercontent.com/69141453/110220048-f154b300-7e77-11eb-86b1-7a0d55de5c89.PNG)
```
10.0.100.3/robots.txt
```

so i went to the **/cyberweekend** path and found the first flag

![4](https://user-images.githubusercontent.com/69141453/110220054-00d3fc00-7e78-11eb-9247-08a64bba51da.PNG)
```
10.0.100.3/cyberweekend/
```

and after that i went to the second **/lfi** path but there was a **?file=** parameter that was written on the <title> so i tried to access multiple files but ended up finding the flag in /etc/passwd 
  
![5](https://user-images.githubusercontent.com/69141453/110220062-1812e980-7e78-11eb-931f-67e9529e69e7.PNG)
```
10.0.100.3/lfi?file=/etc/passwd
```

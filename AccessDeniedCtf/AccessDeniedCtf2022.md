### Web/Safe upload
![](https://i.imgur.com/7Y5pTng.png)

we see that we have a page to upload images

![](https://i.imgur.com/Lb4eEqP.png)

so we intercepted by burp and tried to pass a gif with a gif header but a php type and that worked

![](https://i.imgur.com/JgCS4Ce.png)
![](https://i.imgur.com/dqXqNV0.png)

>accessdenied{php_bu7_n07_php_f1l3_74a148ef}

---

### web/PORTAL DE LOGIN
![](https://i.imgur.com/zpDIX16.png)

we see a login page so we try SQLi, it worked but we need the data because it doesnt return any data, we could use time-based SQLi

![](https://i.imgur.com/VZ6kzIG.png)
```
sqlmap -r reqLogin --dump
```
![](https://i.imgur.com/sHWGn14.png)
![](https://i.imgur.com/gWD6FXU.png)

accessdenied{bl1nd_bl1ndd_blinddd_sql_5fe2db70}

---

### Misc/Shark-1
![](https://i.imgur.com/Div5XQk.png)

we filter by data and follow tcp stream we find ...
![](https://i.imgur.com/DcXGpYh.png)

4ePj5fPz5OXu6eXk+/ex8rPz6LTy69/is/P03+aw8t/wtOPrs/Tf8+6x5uax7uffuebjs7i0seKx/Q==

![](https://i.imgur.com/wXpMPG2.png)

>accessdenied{w1r3sh4rk_b3st_f0r_p4ck3t_sn1ff1ng_9fc3841b1}

---

### Misc/Shark-2

![](https://i.imgur.com/WvftTDz.png)

if we follow tcp stream we find an image
![](https://i.imgur.com/N7hKH3X.png)

>accessdenied{3xtr4ct_0bj3ct5_fr0m_w1r3sh4rk}

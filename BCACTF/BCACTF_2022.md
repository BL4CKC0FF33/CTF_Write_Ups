
### real deal html

![](https://i.imgur.com/mKBoMlG.png)

found the flag in the source 

![](https://i.imgur.com/8gourmT.png)

>bcactf{tH4TZ_D4_R34l_D3Al_cb8949}


---

# Agent Rocket

![](https://i.imgur.com/LkXIKTj.png)

![](https://i.imgur.com/t0NpmlZ.png)

in the source code we find:
```
<!-- The username should be "admin" -->
<!-- The password should be "password" -->
```
when i try them it gives us the following so we change the user-agent header
```
<!-- The name of the device is "BCACTF Rocket Control Panel" in case you forgot. -->
```
![](https://i.imgur.com/Oe3rnhH.png)

>bcactf{u53r_4g3Nt5_5rE_c0OL_1023}

---

### Three Step Trivia

![](https://i.imgur.com/DAWOU1c.png)

we are googling for the answers.

![](https://i.imgur.com/gNVGKKr.png)
![](https://i.imgur.com/M1DT5Qc.png)
![](https://i.imgur.com/t5YC1CG.png)

part 2 we notice the url changes to /7_74

![](https://i.imgur.com/OCnP4wK.png)

then we tried /11_674 and didnt work

![](https://i.imgur.com/8F8iLKY.png)

but it was then we tried /11674 since it wasnt a decimal 

![](https://i.imgur.com/qdVZRQc.png)

part 3

![](https://i.imgur.com/2XddXuN.png)
![](https://i.imgur.com/3wXCiUm.png)



![](https://i.imgur.com/ncY3S7N.png)
sending a burp request didnt work i guess it treated submit as 
```
return event.key == 'Enter';
```
so i edite the html by inspect tools and removed the **visibilit = hidden** style **then clicked the submit button manually** and answer=163

![](https://i.imgur.com/CnVZdK4.png)

>bcactf{sT41r_c4A3_m45T3R_5jfUn9Z}

---

### Cookies

![](https://i.imgur.com/Vs8qziO.png)

we noticed a console printer item and after exploring it we found / adminLogin.html page and adminLogin.js

![](https://i.imgur.com/mfI3A3f.png)
![](https://i.imgur.com/PbsaIHt.png)
![](https://i.imgur.com/rZsUAfZ.png)

so inspect and change guest to admin

![](https://i.imgur.com/GncSdEZ.png)
![](https://i.imgur.com/B08rD2O.png)
![](https://i.imgur.com/pdJ5dhh.png)
![](https://i.imgur.com/pSfN4Jj.png)

change cookie and refresh

>bcactf{u$ers_s33_c00k!es_7oo_863o4t5}

---

### Jason's Web Tarot

![](https://i.imgur.com/kfIrsyp.png)

![](https://i.imgur.com/OhnGKTp.png)

noticed a token cookie that looked like jwt so i decoded it in jwt.io then user jwt_tool to change it
```
python3 jwt_tool.py eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0.eyJpc1N1YnNjcmliZXIiOmZhbHNlLCJpYXQiOjE2NTQzMDA1NzR9. -T  
    eyJhbGciOiJub25lIiwidHlwIjoiSldUIn0.eyJpc1N1YnNjcmliZXIiOnRydWUsImlhdCI6MTY1NDMwMDU3NH0.
```

![](https://i.imgur.com/5rd2HcV.png)

>bcactf{n0_s3cr3t5????!!!?!_38893}

---

### Jason's Web Tarot 2

![](https://i.imgur.com/g1Zj6P5.png)
![](https://i.imgur.com/tJBt65j.png)

checking this we need to bruteforce the jwt key so we use john for that
```
john jwt.txt --format=HMAC-SHA256
    38r4
```
![](https://i.imgur.com/Giq1Nsi.png)
![](https://i.imgur.com/E4LokeH.png)

>bcactf{hm@c_256_yeeeeah_24u9402}

---

checking the documentations on the functions we see in the files provided:

![](https://i.imgur.com/vzACiu8.png)

https://ring-clojure.github.io/ring/ring.middleware.params.html

![](https://i.imgur.com/ztxqsnN.png)

we derive that the part parameter in /story?part= is reading an internal file, so we can try to get the flag.txt but with a bit of traversal

![](https://i.imgur.com/Lvzvm7g.png)

>bcactf{the_envd_jZNCCrTgxR237loZY12JlA}


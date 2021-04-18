# Astral Plane

>Astral Plane is way too big... http://ictf.ninja:62451

>hint: 2 char makes 1


since its a website i visted http://ictf.ninja:62451/robots.txt and found **Disallow: /admin** but when visiting it, it gives 403 so i intercepted by burpsuite and added 
```
X-Rewrite-URL: /admin
X-Forwarded-For: 127.0.0.1
```
that bypassed the 403 but we needed a password and i noticed the below comment
```
<!--<div class="login-help">
  <p>Forgot your password? <a href="/forgoott">Click here to reset it</a>.</p>
</div>-->
```
so i visited **/forgoott** 

![](https://i.imgur.com/HgaDbX5.png)

i tried **password=safebanana&commit=Login** but it seemed that the second a in banana is with a tilde
after googling i found [this unicode websie](https://www.compart.com/en/unicode/U+00E3) that showed ã can be encoded by 
```
U+00E3
```
or
```
a(U+0061) - ◌̃(U+0303)
```
and since the hint said: **2 char makes 1** then we will use the second encoding
and just to make sure that it works without any problem 
```
console.log('safebana\u0303na');
```
then copied the word from the console and passed it
```
password=safebana%CC%83na&commit=Login
```
this is what it looked like in burpsuite

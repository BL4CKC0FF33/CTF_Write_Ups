## Discord

![](https://i.imgur.com/NVeoR2B.png)

>shctf{4ut0b0ts_r013_0u7}

---

## Space Traveler
>Explore space with us.

![](https://i.imgur.com/2VHho0j.png)

print it via writing in console the name of the array

[
  "Guess The Flag",
  "shctf{flag}",
  "You guessed right.",
  "shctf{eighty_seven_thousand_million_suns}",
  "You guessed wrong.",
  "innerHTML",
  "demo",
  "getElementById"
]

>shctf{eighty_seven_thousand_million_suns}

---

## R2D2
>We wouldn't miss the opportunity to make this dad joke.

![](https://i.imgur.com/dZtUhg6.png)

in /robots.txt

>shctf{th1s-aster0id-1$-n0t-3ntir3ly-stable}

---

##  Curious?
>I've been thinking about going on vacation recently and need to know where off Earth I can find these dunes. What sol was this image taken on?

on tineye found the image

![](https://i.imgur.com/5iiXrgl.png)

https://www.space.com/24592-mars-rover-curiosity-dune-jump.html

![](https://i.imgur.com/RgRe84L.png)

>shctf{SOL_533}

---

## Star Pcap

i noticed the only change was happeining in the icmp code so i grabbed it

```
tshark -r star.pcap -T fields -e icmp.code > tmp
```

![](https://i.imgur.com/9HYpRCW.png)

---

##  Netflix and CTF
>I don't like watching anything other than TV shows about Space Heroes.

by exploring the pcap i noticed that the uri seemed funny
```
tshark -r netflix-and-ctf.pcap -T fields -e http.request.uri > tmp
```
removed \n and Lit_ and other stuff 

>shctf{T1m3-is-th3-ultimat3-curr3Ncy}

---

##  Khaaaaaan!
>We have intercepted a messages from different ships, but I can't seem to dcode what they are saying. Can you? 

![](https://i.imgur.com/vKNGcEG.png)

>shctf{WITHOUT_FREEDOM_OF_CHOICE_there_iS_NO_CREATIVITY}

---

## Space buds
>One of the puppies got into the web server. Can you help find out who it was?

![](https://i.imgur.com/mbxcyWS.png)
![](https://i.imgur.com/10FEjP1.png)

>shctf{tastes_like_raspberries}

---

##  Mysterious Broadcast
>There used to be 8 Models of humanoid cylon but now there are only 7. We've located one of their broadcast nodes but we can't decode it. Are you able to decipher their technologies?
http://173.230.134.127

![](https://i.imgur.com/vLJT9GQ.png)
sometimes returns 1,0,~

```
while true ; do curl http://173.230.134.127/seq/213bd5e3-ced7-4583-bbb1-1c92d58c8ae9; done
  1011011011010010110100011000111101101101001001110011000011110011101111010111101~1100011011001011010001101010110010010001111011010011011110100011011000100111011010101100001101011111011001001010110001101100001000101011001110100011101101110110001100001010101011001110100101101000110001011011011010010110100011000111101101101001001110011000011110011101111010111101~110
```
![](https://i.imgur.com/mmaUgmw.png)
![](https://i.imgur.com/hBi5wUy.png)
![](https://i.imgur.com/Z6y71bR.png)

>shctf{AsciiIsA7BitStandard}

---

##  Starman
>How far away from earth was the space car on January, 20 2021 at 1515 UTC? Enter distance in terms of Million Km. (Rounded to two decimals) (e.g shctf{12.34})

https://theskylive.com/planetarium?obj=roadster&date=2021-01-20&h=15&m=15

![](https://i.imgur.com/QEFns0h.png)

>shctf{56.68}

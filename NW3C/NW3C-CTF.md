# NW3C CTF

https://nw3.ctfd.io/challenges

## NCCC_21:

### Q1:
>Welcome or welcome back to the 2021 Mass AG and NW3C and our presentation of our annual capture the flag. Pull up a seat, sit back and let this sweet scenario sink in.
Much like any good book, good movie, or organization; the NW3C started somewhere. Decipher the following text <79 72 69 76 67 76 70 68 66> and enter it as the flag to unlock the next question for this week! While you are solving this problem go ahead and download the evidence file needed for the rest of the challenges! It is available by clicking the link below or at this GoogleDrive Link.
https://drive.google.com/file/d/1lT2FK6W4cLkZMPj8YrEu506mynWtziLX/view?usp=sharing

>79 72 69 76 67 76 70 68 66

from hex then rot13

![](https://i.imgur.com/wbxZsST.png)
>leviticus

### Q1.5:
>You might've been worried about how long it would take to download the "Pinkerton" evidence file. No stress there are a few questions to help ensure the playing field is slightly more level to the eye. Grab the file "SpringBoard.7z" to answer the next question (s) while you wait.
What applicatons' icon is at the left most position of the button bar?
Format: Application Name Example: Safari SpringBoard.7z MD5: 2edad66d46f8e550ab9a8dc6c0434d06

Apple SpringBoard seems like the phone home screen so,icons file seems interesting

```
7z e SpringBoard.7z
file *
strings IconState.plist
```
![](https://i.imgur.com/pKPH3F2.png)

>mobilephone 


### Q1.75:
>Still waiting on the file to download? Not to worry, here is another question to keep the pace.
Located within "SpringBoard.7z" is a flie bearing the Streebog256 hash sum: 2b889486e288fdf3570d03049da09b6a6024b1023f469b802786c86f4ca323b0
What is the files entropy rating as indicated by the Shannon Scale?
Format: d.dd Example: 4.56

![](https://i.imgur.com/WMjVEwl.png)

>LockBackgroundThumbnail.jpg
2b889486e288fdf3570d03049da09b6a6024b1023f469b802786c86f4ca323b0

![](https://i.imgur.com/X2f4GF1.png)

>7.93


### Q2:
>Bread and butter, a delicious breakfast and great way to start this challenge to make sure the evidence you have is the evidence you ought to have! What is the MD5 Hash -Sum of the still archived evidence flie named "Pinkerton"?
Format: ALPHANUMERICMD5HASH Example: b0871386445fd0faedd21ddb0990a903

```
md5sum Pinkerton.tar
```
>ef6313698fc9f6ab2afa064e7e730df4

### Q3:
>What is the version of the Linux Kernel is utlized by the suspect machine?
Format: X.XX.X Example: 14.4.22

```
grep -r "[0-9]\.[0-9][0-9]\.[0-9]" . 
```
>./house/Pinker/Desktop/uname.bin:5.10.0-kali3-amd64
>5.10.0


### Q4:
>Our suspect has recently been practicing their offensive security skills, and as such has extensively been using researching tips and tricks. What is the date and time 24HR UTC of the search concerning PowerShell for offensive security purposes.
Format: YYYY-MM-DD HH:MM:SS Example: 2021-04-10 12:12:12

based on https://support.mozilla.org/bm/questions/1176169
>Firefox stores your history and bookmarks together in a database file named places.sqlite

```bash=
strings ./house/Pinker/.mozilla/firefox/v15k3hyv.default-esr/places.sqlite 
strings ./house/Pinker/.mozilla/firefox/v15k3hyv.default-esr/places.sqlite | grep -i "kali"
sqlitebrowser ./house/Pinker/.mozilla/firefox/v15k3hyv.default-esr/places.sqlite  
```
![](https://i.imgur.com/ZRHfVei.png)

https://www.epochconverter.com/

>Thursday, April 15, 2021 3:01:50.129 PM

YYYY-MM-DD HH:MM:SS
>2021-04-15 15:01:50

### Q5:
>Lorem Ipsum on repeat, sometimes different operating systems store different names differently. However is there a difference? Report the number of different lines, from the files mentioned as the flag.
Format: number(s):
Example: 77

```
grep -i -r "Lorem Ipsum" ./house/Pinker/
    ./house/Pinker/Documents/lorem:
ls -la ./house/Pinker/Documents/
    total 1332
    drwxr-xr-x  3 kali kali   4096 Apr 25 21:57 .
    drwxr-xr-x 17 kali kali   4096 Apr 25 21:57 ..
    -rw-r--r--  1 kali kali 247616 Apr 25 21:57 Conundrum_of_Deepfakes.pdf
    -rwx------  1 kali kali  94193 Apr 25 21:57 CTF_ANSWERS.pages
    -rw-r--r--  1 kali kali 503182 Apr 25 21:57 lorem
    -rw-r--r--  1 kali kali 503182 Apr 25 21:57 Lorem
    drwxr-xr-x  2 kali kali   4096 Apr 25 21:57 SQL_Research
comm -2 -3 <(sort ./house/Pinker/Documents/Lorem) <(sort ./house/Pinker/Documents/lorem) | wc
    30    2435   16304
```
>30

### Q6:
>What is the website which our suspect wishes to be able to post the very first comment after a fresh story drops?
Format: URL Example: https://www.coolwebsite.com

```
strings ./house/Pinker/.mozilla/firefox/v15k3hyv.default-esr/* | grep -i "comment"
```
![](https://i.imgur.com/KAEvlIw.png)

>https://www.pinkbike.com/

### Q7:
>According to the master plan, what is the cool flag?
Format: word(s) Example: floss

```
grep -i -r "master plan" ./house/Pinker/
    Binary file ./house/Pinker/Pictures/master plan workflow.png.arj matches
arj e ./house/Pinker/Pictures/master\ plan\ workflow.png.arj 
eog master\ plan\ workflow.png
```
![](https://i.imgur.com/k8iMsVG.png)
```
strings master\ plan\ workflow.png| grep -i "flag"                               flag is <stringsrkewl>
```

### Q8:
>A call leveraging the following framework occurred: <com.google.android.apps.tachyon/com.google.android.apps.tachyon.telecom.TachyonTelecomConnectionService> The call lasted approximately 95 seconds. What is the date and the at which this call ended? 24HR UTC
Format: YYYY-MM-DD HH:MM:SS
Example: 2021:01:01 12:12:12

```
grep -i -r "com.google.android.apps.tachyon/com.google.android.apps.tachyon.telecom.TachyonTelecomConnectionService" ./house/Pinker/
    Binary file ./house/Pinker/.cache/vmware/drag_and_drop/rhqeoH/com.android.providers.contacts/databases/calllog.db matches
    Binary file ./house/Pinker/Downloads/com.android.providers.contacts/databases/calllog.db matches
strings ./house/Pinker/Downloads/com.android.providers.contacts/databases/calllog.db | grep "com.google.android.apps.tachyon/com.google.android.apps.tachyon.telecom.TachyonTelecomConnectionService" -A 5 -B 5
sqlitebrowser ./house/Pinker/.cache/vmware/drag_and_drop/rhqeoH/com.android.providers.contacts/databases/calllog.db 
```
![](https://i.imgur.com/xLST0Qp.png)

https://www.epochconverter.com/
```
date
1601776417609
Sunday, October 4, 2020 1:53:37.609 AM
2020-10-04 01:53:37

95s=60s+35s
+1.35s
```
>2020-10-04 01:55:12

### Q9:
>What did our suspect search for on Reddit?
Format: word(s) Example: Unicorn farts


```
sqlitebrowser ./house/Pinker/.mozilla/firefox/v15k3hyv.default-esr/places.sqlite 
```
![](https://i.imgur.com/lMmgU1p.png)

>pinkbke articles

### Q10:
>Great job this is the final question for this years CTF!
After researching what OWASP has to offer for web vulnerability scanning our user got to work preparing, working, and practicing! How many instances of Cross-Domain Misconfiguration did our user report during their first automated scan.
Format: Numbers Example : 8675

seems like there is a ZAP output named zap.md in the desktop
```
subl ./house/Pinker/Desktop/ZAP.md 
```
![](https://i.imgur.com/I25epul.png)

>133

---
### extra interesting stuff:
```
xxd ./_master\ plan\ workflow.png.extracted/CA0 | head
    00000000: 4d4d 002a 0000 0008 0004 011a 0005 0000  MM.*............
binwalk ./house/Pinker/Documents/CTF_ANSWERS.pages
```

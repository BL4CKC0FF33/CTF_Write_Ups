
# YouTube

![](https://i.imgur.com/A2Y2Kcy.png)

on their youtibe profile there was a part of the flag https://www.youtube.com/channel/UC_Z36GnY_s8R6_eLvI1R2bg/about

![](https://i.imgur.com/HnWsQKM.png)

and the rest were on 2 of their video's descriptions 

![](https://i.imgur.com/tusDAyp.png)
![](https://i.imgur.com/9aaQUFC.png)
```
GrabCON{th3_qu1ck_
br0wn_f0x_jumps_
0v3r_th3_lazy_d0g}
```
>GrabCON{th3_qu1ck_br0wn_f0x_jumps_0v3r_th3_lazy_d0g}

---
# Find me

![](https://i.imgur.com/DZrhfoD.png)

after searching on google i found https://offen5ive.me/

![](https://i.imgur.com/bZ6YGqW.png)

seems like this is a wrong flag but i kept searching the github
>GrabCON{n0_fl4g_h3r3} 

![](https://i.imgur.com/i6XsUh3.png)
> GrabCON{1_w4s_hid33n_but_y0u_f0und_m3}
---
# E4sy Pe4sy

http://34.102.111.73/login/index.php 

![](https://i.imgur.com/PH0Y3Xw.png)

login by:
```
admin
' or '1'='1
```
>GrabCON{E4sy_pe4sy_SQL_1nj3ct10n} 

---

![](https://i.imgur.com/N8XLTWy.png)

i noticed that the input was given in base64 but after decoding it, it becomes base32 and so on... loop
```
S01ZRENXU1NJVkhGUVZKUkpaRkZNMlNLSTVKVENWU0xLVlZYQVlLVElaTkVVVlRNS0pIRkc2U1dKVkpHV01LWEtaQ1VVVENXTlJORlNVS1dOUkdGS01EVUs1S0dXVlNLS1pDWFFUQ1ROUllFT1VUTE1STFZDTUxFSk5MR1c0Q0lLWVlEQ1RDWEtWMkZNVjJWTkJKRk1SS09MQktHV05EWktKV0U0VlNOTlJTRVdWVEtLSkxWR01CUklOTEdXNUNQS05XRkVSQ1dLWkhFSVVaUk9CTUZFMjJXS1ZKVENXU0tLWlZWVVJTVUdGTEZLVkNGR0ZIVTRSU1ZQRkdXWVRTTUtOVlRLVEtTR0ZSVEFVSlFNUkdGSVZUTUs1SkZNVExaS1pWWElWMk5OTkxFNFZUS0pKTFZJUkxRSlZKR1dNS1RLTVlEU1RDVk5OMkVRVjJXSlpLRk1WTFVKTkpUQ1VTRUtaV0U0VjJTR0JORklVU1dNUkxGTVJMVUpSSldXNkNYS0lZVlVSQ1RHQVlVT1ZDRk1STUU0VktPS0ZKVENTU0VLWldGTVZLUkdGU0U2VkxMTVJNVktNS1dNRktXV09LREtFWUZVVUNWTk4yRVFVWlJPQkdGTVJLT0s1S1RBM0NNS0pWWFFTQ1hLWlNFSVZMTE1SRFZJMjIySlJMR1dUU0hLSVlWVVMyV05OU0ZHVTMySkpGRksyM0VLVklWTVVTVUtSS1hJVDJXR0JORk1WTDJKSk1GRU1DMktOTEVLUlNXS05XRU1VQ1JOTlNFT1ZEMkpGNUZPVkxMR0ZKVEFXU09LWVlVNFJTVEdGWUVJVlJRTlJKRTIyWlZKNUtHV05LR0tWTEZVVkNXTk00VUdVM0xMSkZGSzIzWUtKSldXU1NMS0lZV0dNS1JHRkpFWVZMTEpaTVZLVlNPSlJLVEE1Q1NLNUtWRVZDV0tWSEZNVVJRSVVZRk0yMkdLWkpXVVZTSktaS0RBT0tRS1FZRFNVQ1JIVTZRPT09PQ==
```
https://gchq.github.io/CyberChef/#recipe=From_Base64('A-Za-z0-9%2B/%3D',true)From_Base32('A-Z2-7%3D',true)From_Base64('A-Za-z0-9%2B/%3D',true)From_Base32('A-Z2-7%3D',true)From_Base64('A-Za-z0-9%2B/%3D',true)From_Base32('A-Z2-7%3D',true)From_Base64('A-Za-z0-9%2B/%3D',true)From_Base32('A-Z2-7%3D',true)From_Base64('A-Za-z0-9%2B/%3D',true)From_Base32('A-Z2-7%3D',true)&input=UzAxWlJFTlhVMU5KVmtoR1VWWktVa3BhUmtaTk1sTkxTVFZLVkVOV1UweExWbFpZUVZsTFZFbGFUa1ZWVmxSTlMwcElSa2MyVTFkS1ZrcEhWMDFMV0V0YVExVlZWRU5YVGxKT1JsTlZTMWRPVWtkR1MwMUVWVXMxUzBkWFZsTkxTMXBEV0ZGVVExUk9VbGxGVDFWVVRFMVNURlpEVFV4RlNrNU1SMWMwUTBsTFdWbEVRMVJEV0V0V01rWk5WakpXVGtKS1JrMVNTMDlNUWt0SFYwNUVXa3RLVjBVMFZsTk9UbEpUUlZkV1ZFdExTa3hXUjAxQ1VrbE9URWRYTlVOUVMwNVhSa1ZTUTFkTFdraEZTVlZhVWs5Q1RVWkZNakpYUzFaS1ZFTlhVMHRMV2xaV1ZWSlRWVWRHVEVaTFZrTkdSMFpJVlRSU1UxWlFSa2RYV1ZSVFRVdE9WbFJMVkV0VFIwWlNWRUZWU2xGTlVrZEdTVlpVVFVzMVNrWk5WRXhhUzFwV1dFbFdNazVPVGt4Rk5GWlVTMHBLVEZaSlVreFJTbFpLUjFkTlMxUkxUVmxFVTFSRFZrNU9Na1ZSVmpKWFNscExSazFXVEZWS1RrcFVRMVZUUlV0YVYwVTBWakpUUjBKT1JrbFZVMWROVWt4R1RWSk1WVXBTU2xkWE5rTllTMGxaVmxWU1ExUkhRVmxWVDFaRFJrMVNUVVUwVmt0UFMwWktWRU5UVTBWTFdsZEdUVlpMVWtkR1UwVTJWa3hNVFZKTlZrdE5TMWROUmt0WFYwOUxSRXRGV1VaVlZVTldUazR5UlZGVldsSlBRa2RHVFZKTFQwczFTMVJCTTBOTlMwcFdXRkZUUTFoTFdsTkZTVlpNVEUxU1JGWkpNakl5U2xKTVIxZFVVMGhMU1ZsV1ZWTXlWMDVPVTBaSFZUTXlTa3BHUmtzeU0wVkxWa2xXVFZWVFZVdFNTMWhKVkRKWFIwSk9SazFXVERKS1NrMUdSVTFETWt0T1RFVkxVbE5YUzA1WFJVMVZRMUpPVGxORlQxWkVNa3BHTlVaUFZreE1SMFpLVkVGWFUwOUxXVmxWTkZKVFZFZEdXVVZKVmxKUlRsSktSVEl5V2xaS05VdEhWMDVMUjB0V1RFWlZWa05YVGswMFZVZFZNMHhNU2taR1N6SXpXVXRLU2xkWFUxTk1TMGxaVjBkTlMxSkhSa3BGV1ZaTVRFcGFUVlpMVmxOUFNsSkxWRUUxUTFOTE5VdFdSVlpEVjB0V1NFWk5WVkpSU1ZWWlJrMHlNa2RMV2twWFZWWlRTa3RhUzBSQlQwdFJTMUZaUkZOVlExSklWVFpSUFQwOVBRPT0K

>GrabCON{dayuum_s0n!}

---

# Victim 1 

![](https://i.imgur.com/YrU8USh.png)

http://31.207.115.133:8080/cgi-bin/faststream.jpg?stream=half&fps=15&rand=COUNTER

using this to give us the location of the ip https://www.geolocation.com/en_US?ip=31.207.115.133#ipresult

![](https://i.imgur.com/64EIdNe.png)

>GrabCON{39031}

---
# Victim 2 
![](https://i.imgur.com/XOexNIo.png)

looking at the given picture closely, we find text

![](https://i.imgur.com/axi1ECy.jpg)

google "hotel schennerhof Trentino-Alto Adige"

![](https://i.imgur.com/GNNY7fh.png)
![](https://i.imgur.com/0QxcYTs.png)
```
schennerhof
```

judging from the picture it should be close 
![](https://i.imgur.com/ZmERpKf.png)

>GrabCON{hotelhohenwart}

---

# ProtonDate

![](https://i.imgur.com/xMbMrQk.png)

found this tool https://github.com/1cbf94bc-bc47-42b9-9197-244437fad1e6/protondate

```
git clone https://github.com/1cbf94bc-bc47-42b9-9197-244437fad1e6/protondate
cd protondate
go build
./protondate sc4ry_gh0st@protonmail.com
    The protonmail account belonging to "sc4ry_gh0st@protonmail.com" was potentially created on 2021-09-03 04:37:47 -0400 EDT
```
>GrabCON{03_09_2021}

---

# Gang Busted

![](https://i.imgur.com/ri0MKvd.png)

i used a regex to grep recursively the emails
```
grep -E -o "\b[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,6}\b" -r
    data/com.skype.raider/files/http-cache/b3c69c56c4ca03dba06dd7002d71fbd2.1:sidemaf155@5ubo.com
    data/com.skype.raider/files/http-cache/3f88b0166aa7fb0ff20cfa1fce18a8a5.1:sidemaf155@5ubo.com
```
>skype
>sidemaf155@5ubo.com

![](https://i.imgur.com/fB71zFw.png)

then i catted the file and it gave me the name
```
cat data/com.skype.raider/files/http-cache/b3c69c56c4ca03dba06dd7002d71fbd2.1 
    {"about":null,"avatarHidden":false,"avatarUrl":null,"birthday":null,"birthdayVisibility":"Public","city":null,"country":null,"countryVisibility":"Public","emails":[{"address":"sidemaf155@5ubo.com","type":"Skype","visibility":"ContactsOnly","isVerified":false}],"gender":"0","genderVisibility":"Public","homepage":null,"jobtitle":null,"language":null,"mood":null,"moodHistory":[],"namespace":"live","nameVisibility":"Public","nickname":"evil mike","phones":[],"province":null,"richMood":null,"skypeHandle":"live:.cid.6c41bc4408002e1f","storageMaster":"cosmosdb","structuredMood":null,"timestamp":"8/19/2021 9:08:04 AM +00:00","username":"live:.cid.6c41bc4408002e1f"}
```
>evil mike

then i used evil mike's id to grep and found a database.db

```
grep -E -o "live:.cid.6c41bc4408002e1f" -r | grep -e group
    grep: testoo: binary file matches
    grep: data/com.skype.raider/files/slimcore-aria-cache.data-wal: binary file matches
    grep: data/com.skype.raider/databases/RKStorage: binary file matches
    grep: data/com.skype.raider/databases/s4l-live:.cid.6c41bc4408002e1f.db: binary file matches
    grep: user/0/com.skype.raider/files/slimcore-aria-cache.data-wal: binary file matches
    grep: user/0/com.skype.raider/databases/RKStorage: binary file matches
    grep: user/0/com.skype.raider/databases/s4l-live:.cid.6c41bc4408002e1f.db: binary file matches
sqlitebrowser user/0/com.skype.raider/databases/s4l-live:.cid.6c41bc4408002e1f.db
```

![](https://i.imgur.com/PrvaLvM.png)
![](https://i.imgur.com/f4Bnob7.png)

>GrabCON{Skype_sidemaf155@5ubo.com_31337_Hax0r_Plan_evil_mike}

---

# Website

![](https://i.imgur.com/xr2kmtz.png)

after googling "free website builders" i got: wix, spacesquare, yola, weebly, etc.

https://greatanimalshere.weebly.com/

on firefox it wont open but chrome opened it...

![](https://i.imgur.com/6LOf2dp.png)

>GrabCON{f1nally_y0u_f0und_me_1_h0p3_y0u_enj0y3d!!!}

---





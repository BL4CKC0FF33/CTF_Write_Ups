<h1>Wireshark doo dooo do doo...</h1>

![2](https://user-images.githubusercontent.com/69141453/113491326-e18fb500-949d-11eb-9f82-940f3e7bd9b0.png)

all i did was open it via wireshark then filter/search "http" and follow tcp stream

![22](https://user-images.githubusercontent.com/69141453/113491327-e2c0e200-949d-11eb-8b75-bf1ff6abed48.png)



<h1>Python Wrangling</h1>

![3](https://user-images.githubusercontent.com/69141453/113491352-0f74f980-949e-11eb-9926-5d2b69a6de73.png)

used the given password
```
python3 ende.py -d flag.txt.en                                                                                          2 ⚙
Please enter the password:ac9bd0ffac9bd0ffac9bd0ffac9bd0ff
```
```
picoCTF{4p0110_1n_7h3_h0us3_ac9bd0ff}
```

<h1>Ancient History</h1>

![4](https://user-images.githubusercontent.com/69141453/113491380-58c54900-949e-11eb-8173-f82f8f72008e.png)

as the name says: history so i opened the history tab and found something after ?

![44](https://user-images.githubusercontent.com/69141453/113491381-59f67600-949e-11eb-9300-e5a46b46c906.png)

i tried it as the flag but it seemed not ordered so i used wireshark to see the order and found the flag

![444](https://user-images.githubusercontent.com/69141453/113491382-59f67600-949e-11eb-9d11-18184dcc0284.png)




<h1>Who are you?</h1>

![5](https://user-images.githubusercontent.com/69141453/113491481-118b8800-949f-11eb-9a48-f2c0688359c7.png)

first of all i visted the website, and it seems like i can only access it if i was using a picoBrowser which is the user-agent

![55](https://user-images.githubusercontent.com/69141453/113491482-12241e80-949f-11eb-82da-1576413ac645.png)
![555](https://user-images.githubusercontent.com/69141453/113491485-15b7a580-949f-11eb-8728-b3d0d362085d.png)

then i had to edit the referer header

![5555](https://user-images.githubusercontent.com/69141453/113491487-15b7a580-949f-11eb-9a0c-4abea6ead944.png)
![55555](https://user-images.githubusercontent.com/69141453/113491488-16503c00-949f-11eb-8c20-f6530304a9c0.png)
![555555555555](https://user-images.githubusercontent.com/69141453/113491496-1f410d80-949f-11eb-99c8-1398c0b89ae7.png)
![55555555](https://user-images.githubusercontent.com/69141453/113491492-1bad8680-949f-11eb-990a-941f02ba6769.png)
![555555555](https://user-images.githubusercontent.com/69141453/113491493-1c461d00-949f-11eb-9f09-fe36457be8c9.png)
![5555555555](https://user-images.githubusercontent.com/69141453/113491494-1cdeb380-949f-11eb-8c26-2a3e9b909641.png)
![555555](https://user-images.githubusercontent.com/69141453/113491491-1b14f000-949f-11eb-8ef2-bbf2e9ea4ca5.png)


finally, gave us the flag

![55555555555](https://user-images.githubusercontent.com/69141453/113491495-1cdeb380-949f-11eb-972d-68fe30d5bc2a.png)
```
picoCTF{http_h34d3rs_v3ry_c0Ol_much_w0w_8d5d8d77}
```































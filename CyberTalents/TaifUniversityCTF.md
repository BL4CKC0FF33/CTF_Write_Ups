<h1>Time Zone - Digital Forensics</h1>

we were given a registry file, i opened it via Registry viewer and googled "time zone in registry files" and "in /control/timezoneinformation" was the result

![3](https://user-images.githubusercontent.com/69141453/112745473-86216c80-8f5d-11eb-873b-88100700d98e.PNG)

turened out the flag was EYGPT in md5 and wraped around flag{}???



<h1>Beyond Limitations - Web Security</h1>

as the title says, theres a SQLi in the login, after googling we found this payload

![11](https://user-images.githubusercontent.com/69141453/112745538-0ea00d00-8f5e-11eb-8e70-00a5b03440e1.PNG)

![111](https://user-images.githubusercontent.com/69141453/112745527-f92ae300-8f5d-11eb-80c6-06ad86dc8132.PNG)

![1](https://user-images.githubusercontent.com/69141453/112745546-18297500-8f5e-11eb-8086-f753dd527549.PNG)



<h1>Weird Vigenère - Cryptography</h1>

we were given this txt file and doesnt make sense but there was something simular which is traditional morse.
![2222](https://user-images.githubusercontent.com/69141453/112745554-2e373580-8f5e-11eb-8cf2-6d4c2948efee.PNG)

![222](https://user-images.githubusercontent.com/69141453/112745568-4dce5e00-8f5e-11eb-883d-f95f6353cf01.PNG)

then we coded a python code that does the translation for us, then removed the \n by sublime

![22](https://user-images.githubusercontent.com/69141453/112745622-b289b880-8f5e-11eb-97f3-482649984ab1.PNG)

```
q= ["dah-dah-dah-dah-dah", "di-dah-dah-dah-dah", "di-di-dah-dah-dah", "di-di-di-dah-dah", "di-di-di-di-dah", "di-di-di-di-dit", "dah-di-di-di-dit", "dah-dah-di-di-dit", "dah-dah-dah-di-dit", "dah-dah-dah-dah-dit", "di-dah", "dah-di-di-dit", "dah-di-dah-dit", "dah-di-dit", "dit", "di-di-dah-dit", "dah-dah-dit", "di-di-di-dit", "di-dit", "di-dah-dah-dah", "dah-di-dah", "di-dah-di-dit", "dah-dah", "dah-dit", "dah-dah-dah", "di-dah-dah-dit", "dah-dah-di-dah", "di-dah-dit", "di-di-dit", "dah", "di-di-dah", "di-di-di-dah", "di-dah-dah", "dah-di-di-dah", "dah-di-dah-dah", "dah-dah-di-dit"];
p= ["0","1","2","3","4","5","6","7","8","9","A","B","C","D","E","F","G","H","I","G","K","L","M","N","O","P","Q","R","S","T","U","V","W","X","Y","Z"];

x= "dah-dah-dah-dah-dah dah-di-di-dah di-di-di-di-dah dah-di-dah-dit dah-di-di-di-dit di-di-dah-dit di-di-di-dah-dah dah-dah-dah-dah-dah dah-di-di-di-dit dah-di-di-dit di-di-dah-dah-dah di-dah dah-dah-di-di-dit di-di-di-di-dit di-di-di-di-dit dah-dah-dah-dah-dah di-di-dah-dah-dah di-dah di-di-di-di-dah dah-dah-di-di-dit di-di-di-dah-dah di-di-di-dah-dah dah-dah-di-di-dit di-di-di-di-dah di-di-di-dah-dah dit di-di-di-di-dah dah-di-di-dit di-di-di-dah-dah di-di-di-dah-dah dah-dah-di-di-dit dah-dah-dah-dah-dit di-di-dah-dah-dah di-dah-dah-dah-dah di-di-dah-dah-dah di-dah-dah-dah-dah di-di-dah-dah-dah di-dah-dah-dah-dah di-di-di-dah-dah di-di-di-di-dah di-di-di-di-dah di-di-dah-dah-dah di-di-di-dah-dah dah-dah-dah-dah-dah di-di-di-di-dit dah-di-di-di-dit di-di-di-dah-dah di-di-di-dah-dah di-di-dah-dah-dah di-di-di-di-dit di-di-dah-dah-dah di-di-di-di-dit di-di-di-di-dit dah-dah-dah-dah-dit di-di-di-dah-dah dah-dah-dah-dah-dah dah-dah-di-di-dit di-di-di-di-dit di-di-di-dah-dah di-di-dah-dah-dah di-di-di-dah-dah di-dah di-di-di-di-dit dah-dah-dah-dah-dah di-di-di-di-dah dah-dah-dah-di-dit di-di-di-dah-dah di-di-di-dah-dah di-di-di-dah-dah di-di-di-di-dah dah-di-di-di-dit di-di-di-di-dah di-di-dah-dah-dah di-dah dah-dah-di-di-dit dah-dah-di-di-dit di-di-di-dah-dah dah-dah-dah-dah-dah di-di-di-di-dit dah-dah-di-di-dit di-di-dah-dah-dah di-di-di-dah-dah dah-di-di-di-dit dah-dah-dah-di-dit di-di-di-dah-dah di-di-di-di-dah di-di-di-dah-dah di-di-di-di-dit di-di-di-di-dah dah-dah-dah-di-dit dah-dah-di-di-dit di-di-di-di-dah di-di-di-dah-dah di-di-di-di-dah di-di-di-di-dah dah-dah-di-di-dit di-di-dah-dah-dah di-di-di-dah-dah di-di-dah-dah-dah di-dah-dah-dah-dah di-di-di-di-dit di-di-di-di-dah di-di-di-dah-dah di-di-dah-dah-dah di-di-di-dah-dah di-di-di-dah-dah di-di-di-di-dah dit dah-di-di-di-dit di-di-di-di-dah di-di-di-dah-dah di-dah-dah-dah-dah dah-di-di-di-dit dit di-di-di-di-dah dah-dah-di-di-dit di-di-di-dah-dah dah-di-di-dit dah-di-di-di-dit dah-dah-di-di-dit dah-di-di-di-dit dah-dah-di-di-dit di-di-dah-dah-dah dah-dah-dah-dah-dit di-di-dah-dah-dah dah-dah-dah-dah-dah di-di-di-di-dah dah-di-dit di-di-di-di-dah di-di-di-di-dah di-di-di-di-dah di-di-dah-dit di-di-di-di-dit di-dah dah-dah-di-di-dit dah-di-di-dit di-di-di-di-dit di-di-di-di-dah di-di-di-di-dah di-dah-dah-dah-dah di-di-di-di-dit di-di-di-di-dit di-di-di-di-dit di-di-dah-dit di-di-di-di-dah dah-di-di-di-dit di-di-di-di-dah di-dah-dah-dah-dah di-di-di-di-dah dah-di-di-dit di-di-di-di-dit di-di-dah-dit di-di-di-di-dit dah-dah-di-di-dit di-di-di-di-dit di-dah-dah-dah-dah di-di-di-di-dah dit di-di-di-di-dah dah-di-dit di-di-di-di-dah dah-dah-di-di-dit di-di-di-di-dah dah-di-di-di-dit di-di-di-di-dah dah-dah-di-di-dit dah-dah-di-di-dit dah-di-dit di-di-di-di-dah dah-dah-dah-dah-dah dah-di-di-di-dit di-di-di-dah-dah dah-di-di-di-dit di-di-dah-dit dah-dah-di-di-dit di-di-dah-dah-dah dah-di-di-di-dit di-di-dah-dit dah-di-di-di-dit dit dah-di-di-di-dit di-dah-dah-dah-dah dah-di-di-di-dit dah-di-di-di-dit dah-di-di-di-dit dah-di-dah-dit dah-di-di-di-dit di-dah-dah-dah-dah dah-di-di-di-dit dah-dah-di-di-dit ";
x=x.split();

for i in range(len(x)):
	for j in range(len(q)):
		if x[i]==q[j]:
			print(p[j]);
			continue;


```


which gave us a hex (starts by 0x) and there was a weird part in it with a { and } that looked weird but there was a hint "look above you" it needed decoding

![2](https://user-images.githubusercontent.com/69141453/112745627-bcabb700-8f5e-11eb-914b-e5c1a9a05801.PNG)

so we tried beaufort cipher with knowing part of plaintext and that gave the key which was "roof"

![22222](https://user-images.githubusercontent.com/69141453/112745798-d39ed900-8f5f-11eb-94df-b7c0a406363a.PNG)

then we should have used that key with beaufort cipher that would have gave the flag

![222222](https://user-images.githubusercontent.com/69141453/112745815-021cb400-8f60-11eb-8bd8-6306ea9ec351.PNG)




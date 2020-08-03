this challenge is in the Warm Up section.
by 
```
cat caesarmirrior.txt | caesar
```

we get the 1st part of the flag

<img width="789" alt="Screen Shot 2020-08-03 at 12 02 51 PM" src="https://user-images.githubusercontent.com/69141453/89165889-e2282280-d581-11ea-93a3-0f17fb78cfc2.png">

but the right half of the text seems off, but if u noticed, the name of the challenge is "Caesar MIRRIOR" and the left most side of the left paragraph looks like the right most side of the right paragraph, which might mean that is is reflected, like a mirrior.
so i tried copying the right paragraph and reversing the string

<img width="362" alt="Screen Shot 2020-08-03 at 12 00 24 PM" src="https://user-images.githubusercontent.com/69141453/89166256-70040d80-d582-11ea-9e28-a3d2583b099c.png">

```python
str=""bf V !erugrtbg ghc bg ahs sb gby n fnj ftavug rivgnibaav qan jra ch xavug bg sb genc gfevs ruG !frhdvauprg SGP pvffnyp tavuglerir gba fv gv gho gengf gnret qan rqvu bg tavleg rxvy g'abq V bq hbl gho _n_av_ fv tnys rug sb genc rxnz qan leg bg reru rqhypav rj qyhbuf ?fravyjra qqn rj qyhbuF ?ryvujugebj uthbar fv fravy lanz jbU ?ynpvegrzzlf n avugvj ferggry sb renhdf qvybf rug gn gfbzyn rj reN .rz bg uthbar }abvgprysre fv tnys ehbl sb genc qevug ruG ebs tnys fvug gvzohf bg qrra hbl gnug ,rpneo lyehp tavarcb rug qan kvsrec tnys lyehp tavfbyp n av qar bg ,frebpferqah fvug bg erucvp enfrnp rug xyvz qyhbp !ynqrz n lht enfrnP " # initial string"
stringlength=len(str) # calculate length of the list
slicedString=str[stringlength::-1] # slicing 
print (slicedString) # print the reversed string
```
from https://www.educative.io/edpresso/how-do-you-reverse-a-string-in-python 

then i ran:
```
python3 reverse.py | caesar
```

which resutled in giving us the 2nd and the 3rd part of the flag

<img width="1423" alt="Screen Shot 2020-08-03 at 12 03 17 PM" src="https://user-images.githubusercontent.com/69141453/89166686-10f2c880-d583-11ea-81d2-735583ebe5ab.png">

<img width="1425" alt="Screen Shot 2020-08-03 at 12 03 39 PM" src="https://user-images.githubusercontent.com/69141453/89166743-27008900-d583-11ea-88d2-43be580afdbd.png">

# Heads-UP 

given a txt file that contains longitude and latitude at first nothing seemed off about it and i plotted it
```
43.39893, 82.86786	   	       	      	   	    	    
42.75697, 82.95575	  	     	      	      	    	    	     
39.71761, 82.69208      	     	     	    	     	     	   
38.96995, 81.11005   		      		 	       	    	   
46.86946, 82.25263	     	 	  	     	    	       
47.99899, 79.44013	  	     		     		       	   
45.03653, 54.47919   	      	  	    	  	   	      	       
52.22264, 52.63349	 		    	    	      	     	     
52.70457, 55.70966   		
57.5231, 58.43427
57.33384, 53.33661
45.59278, 68.54169
42.8859, 72.93622
33.44275, 71.52997
32.48413, 67.04755
31.59008, 62.38935
21.302, 80.23115
17.99163, 57.99482
42.82146, 57.46747
```
![](https://i.imgur.com/m12MMKZ.png)

but then i noticed something

![](https://i.imgur.com/Olygr64.png)

looks like whitespace cipher so i searched for tools until i found stegsnow 
```
stegsnow -C headup.txt
```
but this gave nonsense so i needed a password, the name was a hint (heads up = on earth look up = start), which was in the plotted picture, it was constellations, after googling it and trying constellations names, "orion" was the password 

```
stegsnow -C -p "orion" headup.txt
```

```
ICTF{Fr0m_Out3r_W0RLD} 
```
[BL4CKC0FF33 ☕](https://github.com/BL4CKC0FF33/)


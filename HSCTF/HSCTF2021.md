# misc/pallets-of-gold
> It doesn't really look like gold to me...

open it via stegsolv
```
java -jar /opt/stegsolve.jar
```
![](https://i.imgur.com/AFp8RpN.png)

>flag{plte_chunks_remins_me_of_qils}

----------------------------------------------------------------------
# misc/LSBlue
> Orca watching is an awesome pastime of mine!

open it via stegsolv ans use the LSB function
```
java -jar /opt/stegsolve.jar
```
![](https://i.imgur.com/o5UiNJZ.png)

>flag{0rc 45_4r3nt_6lu3_s1 lly_4895131}

----------------------------------------------------------------------
# web/NRC
> Find the flag :)
no-right-click.hsc.tf

clicking CTRL+U and finding a link view-source:https://no-right-click.hsc.tf/useless-file.css 

>flag{keyboard_shortcuts_or_taskbar} 

----------------------------------------------------------------------
# misc/Return of the Intro to Netcat
>hey, netcat seems fun! (with a twist)
nc return-of-the-intro-to-netcat.hsc.tf 1337

```
nc return-of-the-intro-to-netcat.hsc.tf 1337
== proof-of-work: enabled ==
please solve a pow first
You can run the solver with:
    python3 <(curl -sSL https://goo.gle/kctf-pow) solve s.AACF.AAD1NSzaviS15ewE/zJ3lZFb
===================

Solution? s.AAB8PXCCRqChJ7WzDBUzjUv6t61ISzLAaSuK5R5W0k/y1gafBydG/gOOgIRgsaudj9OR7ZB2h2PhArYDhQEPFps3wZH2R7NodkCReoUPXoZxHRY2ntcztiZck5lKGxq8bmoYdpW4LWHQ+oTiJ+lVh0P6aB3vN63LXwzzUrhX4RLtfR+IjzXGn29JklaAZST/H37zpebVpF+8Np7BdrWHg1sF
Correct
You got it! Here's what you're looking for: flag{the_cat_says_meow}
```
got the solution from another terminal
```
python3 <(curl -sSL https://goo.gle/kctf-pow) solve s.AACF.AAD1NSzaviS15ewE/zJ3lZFb
Solution: 
s.AAB8PXCCRqChJ7WzDBUzjUv6t61ISzLAaSuK5R5W0k/y1gafBydG/gOOgIRgsaudj9OR7ZB2h2PhArYDhQEPFps3wZH2R7NodkCReoUPXoZxHRY2ntcztiZck5lKGxq8bmoYdpW4LWHQ+oTiJ+lVh0P6aB3vN63LXwzzUrhX4RLtfR+IjzXGn29JklaAZST/H37zpebVpF+8Np7BdrWHg1sF
```

>flag{the_cat_says_meow}

----------------------------------------------------------------------
# misc/seeded-randomizer
> There are at least two types of randomizers in Java, one that is purely random and one that is seeded (that is pseudorandom). Please fix this code to output the correct flag (note the flag format, and a sample has been provided).

![](https://i.imgur.com/UC98nFA.png)

basically, in java theres 2 ways to randomize number, 1-truly random 2-fake random (can give u the same thing given a specific SEED value) 

![](https://i.imgur.com/D5cuDLY.png)
with the SEED random, u can guess the next random numbers, no matter how many times u run it, its the same

heres how it acts without the seed
![](https://i.imgur.com/CXCKHKB.png)
in short, 
random() returns a random number
random(x) where x is the seed, will return a psudo-random, meaning u can predict/know the pattern cuz its the same everytime

``` java=
import java.util.Random;

public class SeededRandomizer {

	public static void display(char[] arr) {
		for (char x: arr)
			System.out.print(x);
		System.out.println();
	}

	public static void sample() {
		Random rand = new Random(79808677);

		char[] test = new char[12];
		int[] b = {9, 3, 4, -1, 62, 26, -37, 75, 83, 11, 30, 3};
		for (int i = 0; i < test.length; i++) {
			int n = rand.nextInt(128) + b[i];
			test[i] = (char)n;
		}
		display(test);
	}

	public static void main(String[] args) {
		sample();
		// Instantiate another seeded randomizer below (seed is integer between 0 and 1000, exclusive):
		char[] flag = new char[33];
		int[] c = {13, 35, 15, -18, 88, 68, -72, -51, 73, -10, 63, 
				1, 35, -47, 6, -18, 10, 20, -31, 100, -48, 33, -12, 
				13, -24, 11, 20, -16, -10, -76, -63, -18, 118};

		for (int j = 0; j <= 1000; j++) {
			Random rand = new Random(j);

			for (int i = 0; i < flag.length; i++) {
				int n = rand.nextInt(128) + c[i];
				flag[i] = (char)n;
			}
			display(flag);
		}
	
	}

}
```

1-i copied the highlighted from the sample() function to the main() function
2-i looped 0-1000 cuz thats what the comment said

>flag{s33d3d_r4nd0m1z3rs_4r3_c00l}

----------------------------------------------------------------------
# misc/glass-windows
>I found a cool glass texture.

open it via stegsolv
```
java -jar /opt/stegsolve.jar
```
![](https://i.imgur.com/EmIYDqQ.png)

>flag{this_is_why_i_use_premultiplied_alpha}

----------------------------------------------------------------------
# web/message-board
> Your employer, LameCompany, has lots of gossip on its company message board: message-board.hsc.tf. You, Kupatergent, are able to access some of the tea, but not all of it! Unsatisfied, you figure that the admin user must have access to ALL of the tea. Your goal is to find the tea you've been missing out on.
Your login credentials: username: kupatergent password: gandal
Server code is attached (slightly modified).

loggedin by kupatergent:gandal

j%3A%7B%22userID%22%3A%22972%22%2C%22username%22%3A%22kupatergent%22%7D

![](https://i.imgur.com/3GsIUbY.png)

in the app.js 
![](https://i.imgur.com/StaFiRJ.png)

![](https://i.imgur.com/zgIozxs.png)
![](https://i.imgur.com/vyxUadW.png)

>flag{y4m_y4m_c00k13s}















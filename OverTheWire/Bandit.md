https://overthewire.org/wargames/bandit/

<h1>level0:</h1>

as the level0 said i ssh-ed to the server: 
```
ssh 'bandit0'@bandit.labs.overthewire.org -p 2220
```
pass: bandit0

and there i searched for files

```
ls -la
cat readme
```
in the readme file the bandit1 password was found
so i exited to connect to level1 
```
exit
```
<h1>level1:</h1>

```
ssh 'bandit1'@bandit.labs.overthewire.org -p 222
```
pass: boJ9jbbUNNfktd78OOpsqOltutMc3MY1

there seems to be a file thats named -
after googling it i found out that to read it i had to use
```
cat ./-
```

<h1>level2:</h1>

```
ssh 'bandit2'@bandit.labs.overthewire.org -p 222
```
pass: CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9

theres a file with spaces in its name
```
cat 'spaces in this filename'
```

<h1>level3:</h1>

```
ssh 'bandit3'@bandit.labs.overthewire.org -p 222
```
pass: UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK
```
cat ./inhere/.hidden
```

<h1>level4:</h1>

```
ssh 'bandit4'@bandit.labs.overthewire.org -p 222
```
pass: pIwrPrtPN36QITSp3EQaw936yaFoFgAB
```
file ./-file0*
cat ./inhere/-file07
```
fisrtly i had to know which is human-readable > ASCII and then read it


<h1>level5:</h1>

```
ssh 'bandit5'@bandit.labs.overthewire.org -p 222
```
pass: koReBOKuIDDepwhWk7jZC0RTdopnAYKh
```
find ./inhere/ -size 1033c
cat ./inhere/maybehere07/.file2
```
the size was given so i searched by that and found that .file2 had the criteria 

<h1>level6:</h1>

```
ssh 'bandit6'@bandit.labs.overthewire.org -p 222
```
pass: DXjZPULLxYr17uwoI01bNLQbtFemEgo7
```

```




























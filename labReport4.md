# Lab Report 4 - Vim (Week 7)



## Step 4 - Log into ieng6
![4.4 Screenshot](4.4Screenshot.jpg)

**Keystrokes**:
```
s s h <space> e s s h a r m a <shift>2 i e n g 6 . u c s d . e d u <enter>
```

The `ssh` command followed by my username `essharma@ieng6.ucsd.edu` followed by `<enter>` allowed me to log into the ieng6 remote computer server


## Step 5 - Clone your fork of the repository from your Github account
![4.5 Screenshot](4.5Screenshot.jpg)

**Keystrokes**:
```
g i t <space> c l o n e <space> <command>v <enter>
```

The `git` command followed by `clone` followed by `git@github.com:eshaan-s18/lab7.git` (which was pasted using `<command>v` because the SSH URL was copied on my computer) followed by `<enter>` allowed me to clone my fork of the repository from my Github account


## Step 6 - Run the tests, demonstrating that they fail
![4.6 Screenshot](4.6Screenshot.jpg)

**Keystrokes**:
```
c d <space> l a b 7 <enter>
l s <enter>
b a s h <space> t e s t . s h <enter>
```

The `cd` command followed by `lab7` followed by `<enter>` allowed me to move into the `lab7` directory.
<br>
The `ls` command followed by `<enter>` allowed me to see the files in the `lab7` directory including the `test.sh`, `ListExamples.java`, and `ListExamplesTests.java` files.
<br>
The `bash` command followed by `test.sh` followed by `<enter>` allowed me to run the `test.sh` shell file to run the tests in `ListExamplesTests.java` to demonstrate that they fail as seen by the `Tests run: 2,
Failures: 1` line of the output


## Step 7 - Edit the code file to fix the failing test
![4.7.1 Screenshot](4.7.1Screenshot.jpg)
![4.7.2 Screenshot](4.7.2Screenshot.jpg)
![4.7.3 Screenshot](4.7.3Screenshot.jpg)

**Keystrokes**:
```
v i m <space> L i <tab> . <tab> <enter>
4 3 J
1 1 L
X
I
2
<esc> : w q <enter>
```

The `vim` command followed by `Li <tab>` (which autofilled `ListExamples` in my terminal) followed by `. <tab>` (which autofilled `.java` in my terminal) followed by `<enter>` allowed me to open *vim* to edit th `ListExamples.java` file
<br>
The `43J` keystroke in vim took me down 43 lines to the line with `index1 += 1;`
<br>
The `11L` keystroke in vim took me right 11 space on the `index1 += 1;` line to the 11th character from the right `1`
<br>
The `X` keystroke in vim deleted the `1` character, leaving `index +=1;` on the line
<br>
The `I` keystroke in vim opened up *insert mode*
<br>
The `2` keystroke inserted the character `2` in the position to the left of where my cursor was (in between the `x` and `+` in the `index +=1;` line)
<br>
These keystrokes allowed me to change the `index1 += 1;` line to `index2 += 1;`
<br>
Finally, the `<esc>` command followed by `:wq` followed by `<enter`> allowed me to successfully save and exit the edited and fixed `ListExamples.java` file.


## Step 8 - Run the tests, demonstrating that they now succeed
![4.8 Screenshot](4.8Screenshot.jpg)

**Keystrokes**:
```
b a s h <space> t e s t . s h <enter>
```
The `bash` command followed by `test.sh` followed by `<enter>` allowed me to run the `test.sh` shell file to run the tests in `ListExamplesTests.java` to demonstrate that they now succeed as seen by the `OK (2 tests)` line of the output

## Step 9 - Commit and push the resulting change to your Github account
![4.9 Screenshots](4.9Screenshot.jpg)

**Keystrokes**:
```
g i t <space> s t a t u s <enter>
g i t <space> a d d <space> . <enter>
g i t <space> s t a t u s <enter>
g i t <space> c o m m i t <space> - m <space> " F i x e d <space> L i s t E x a m p l e s . j a v a " <enter>
g i t <space> p u s h
```

The `git` command followed by `status` followed by `<enter>` allowed me to see what branch I was in (`main`) and if my changed files (`ListExamples.java`) were staged for commit (they were not)
<br>
My changes were not staged for commit, so I used the `git` command followed by `add` followed by `.` followed by `<enter>` to stage all the files I changed (`ListExamples.java`)
<br>
I ran the `git` command followed by `status` followed by `<enter>` again to see if my changed files were staged for commit (they were)
<br>
The `git` command followed by `commit` followed by `-m` followed by `Fixed ListExamples.java` allowed my to commit my changes to the `ListExamples.java` file  with a message of my choosing ("Fixed ListExamples.java")
<br>
The `git` command followd by `push` allowed me to push my changes to the `main` branch in the repository on my Github account


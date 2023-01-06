### Class Participation Assignment #1 - Solution 

Task 1: 
* Open up the manual page for the `cp` command. Skim through the information and find what -u option does and what it stands for. 
    
* Quit the `man` buffer page and come back to your command prompt.  

> **Tip** - Shell commands can get extremely complicated. No one can possibly learn all of these arguments, of course. So you will probably find yourself referring to the manual page frequently.
>
> **Tip** - If the manual page within the Terminal is hard to read , the manual exists online too. For example, here is the linux manual page for `cp`. https://man7.org/linux/man-pages/man1/cp.1.html In addition to the arguments, you can also find good examples online; ***Google is your friend.***
***

Task 2: 

* Use the `-l` option for the `ls` command to display more information for each item in the directory. What additional information is provided that you don't see with the bare `ls` command? 

<details><summary>SOLUTION</summary>
<p>

```
total 7
drwxrwxrwx 2 pdrodrig pi-jdragon 4096 Jan  4 11:13 genomics_data
drwxrwxrwx 2 pdrodrig pi-jdragon 4096 Jan  4 11:13 other
drwxrwxrwx 2 pdrodrig pi-jdragon 4096 Jan  4 11:13 raw_fastq
-rwxrwxrwx 1 pdrodrig pi-jdragon  377 Jan  4 11:13 README.txt
drwxrwxrwx 2 pdrodrig pi-jdragon 4096 Jan  4 11:13 reference_data
```
Each line of output represents a file or a directory. The directory lines start with `d`. It also includes the name of the owner of the file, when the file was last modified, and whether the current user has permission to read and write the file. 

</p>
</details>

## Class Participation Assignment #1 
For these "short" assignments you will have 24 hours to submit via Blackboard. **Late assignments will not be accepted.** My suggestion is to complete while in-class and submit prior to leaving for the day. I will try my best to leave ~10 minutes at the end of class for students to complete during class.  

### Directions for Students: 
Open a new Microsoft Word Document to answer questions 1-3. The first four lines of your document should contain the following:  
+ Your name
+ MMG232
+ Today's date
+ Class Participation Assignment #1   

### Task 1: 
* On Terminal, open the manual page for the `cp` command. Skim through the information. 

Questions to Answer for Task 1:   
1)  What does the -u option stand for and what does it do?   
2)  Which option would you use to explain what is being done (i.e. verbose)?   
    
* Quit the `man` buffer page and come back to your command prompt.  

> **Tip** - Shell commands can get extremely complicated. No one can possibly learn all of these arguments, of course. So you will probably find yourself referring to the manual page frequently.

> **Tip** - If the manual page within the Terminal is hard to read , the manual exists online too. For example, here is the linux manual page for `cp`. https://man7.org/linux/man-pages/man1/cp.1.html In addition to the arguments, you can also find good examples online; ***Google is your friend.***


### Task 2: 
* Use the `-l` option for the `ls` command to display more information for each item in the `unix_lesson` folder. 

Question to Answer for Task 2:   
3) Submit a screenshot of your screen and underneath describe what additional information is provided that you don't see with the bare `ls` command. 
# Class Schedule 

## Tuesday, January 17th 

| Time |  Topic  | 
|:-----------:|:----------:|
| ~ 30 mins |  Syllabus & [Intro to MMG232](../lectures/Intro_to_workshop.pdf) | 
| ~30 mins | [Introduction to Shell](../lessons/01_week1_mmg232.md) | 


## Before the next class:

Please complete the Class Participation Assignment #1:
   * **Remember to Copy over** your the answers to a Microsoft Word Document on your local computer. 
   * **Upload the text file** to [Blackboard](https://bb.uvm.edu/) before the next class. Late assignments will not be accepted. 

### Questions?
* Please email me if you have questions or would like to schedule a meeting: princess.rodriguez@med.uvm.edu  
Office: Given Courtyard S357  
Office phone number: 802-656-1718 (Monday-Friday; 8am to 5pm)

***

## Thursday, January 19th 

| Time |  Topic  | 
|:-----------:|:----------:|
| ~ 45 mins |  [Intro to MMG232](../lectures/Intro_to_workshop.pdf) | 

### Before the next class:

I. Please **study the contents** and **work through all the code** within the following lessons:

1. [Permissions and Environment Variables](../lessons/07_permissions_and_environment_variables.md)

      <details>
       <summary><i>Click here for a preview of this lesson</i></summary>
         <br>When using a multi-user system like the O2 cluster, you may want to limit access to your work. Permissions exist to clearly delineate who has the ability to read, write and execute your files.<br><br>
         Also, when working in a UNIX system, there are a core set of default variables that control the behavior of your command-line. One of the most important of these is the $PATH variable, which tells the system where to look for commands that you give it. <br><br>This lesson will cover:<br>
             - Interpreting and modifying existing permissions<br>
             - Querying environmental variables<br>
             - Reading and appending to the $PATH variable<br><br>
        </details>

2. [Introduction to High-performance computing](../lessons/08_HPC_intro_and_terms.md)

      <details>
       <summary><i>Click here for a preview of this lesson</i></summary>
         <br>Now that you had a chance to explore the O2 cluster, let's focus on the components of this system, how it is different than your personal computer and the advantages that it offers in terms of parallelization. <br><br>This lesson will cover:<br>
             - Differentiating a high-performance computing cluster like O2 from your personal computer<br>
             - Discuss the large parallelization advantage that O2 has over a personal computer<br><br>
        </details>

> **NOTE:** To run through the code above, you will need to be **logged into O2** and **working on a compute node** (i.e. your command prompt should have the word `compute` in it). For login instructions, please see above.

II. **Complete the exercises**:
   * Each lesson above contain exercises; please go through each of them.
   * **Copy over** your the answers for the exercises into a plain text file on your local computer, using Notepad++, TextWrangler or similar. 
     * *Please do not copy all of the content from your Terminal, just the answers.*
   * **Upload the text file** to [Dropbox](https://www.dropbox.com/request/CJQDnQOzav8LZ8SkiojW) the **day before the next class**.
   
### Questions?
* ***If you get stuck due to an error*** while runnning code in the lesson, [email us](mailto:hbctraining@hsph.harvard.edu) 
* Post any **conceptual questions** that you would like to have **reviewed in class** [here](https://PollEv.com/hbctraining945).

***

## Tuesday, January 24th 

| Time |  Topic  | Instructor |
|:-----------:|:----------:|:--------:|
| 9:30 - 10:00 | Self-learning lessons review | Will |
| 10:00 - 11:00 | [Introduction to the O2 cluster](../lectures/HPC_intro_O2_July2022.pdf) | Will |
| 11:00 - 11:30 | [Exercise](../activities/sbatch_exercise.md) ([answer key](https://raw.githubusercontent.com/hbctraining/Intro-to-shell-flipped/master/activities/sbatch_exercise_answer.txt))| Jihe |
| 11:30 - 11:45 | Introduction to the O2 cluster - data storage| Jihe |
| 11:45 - 12:00 | [Wrap up](../lectures/shell-workshop-wrapup.pdf) | Jihe |

***

## Dataset
[Introduction to Shell: Dataset](https://www.dropbox.com/s/3lua2h1oo18gbug/unix_lesson.tar.gz?dl=1)

## Answer keys
* [Day 1 Exercises](../homework/Day1_answer_key.txt)
* [Day 2 Exercises](../homework/Day2_answer_key.txt)


## Advanced bash commands
If you are interested in learning some more advanced tools for working on the command-line, we encourage you to walk-through the materials linked below:

* [More fun with bash commands](../lessons/extra_bash_tools.md)
* [Advanced bash commands (aliases, copying files, and symlinks)](https://hbctraining.github.io/Intro-to-rnaseq-hpc-salmon-flipped/lessons/more_bash_cluster.html)

## Resources

Cheat sheets:
* [http://fosswire.com/post/2007/08/unixlinux-command-cheat-sheet/](http://fosswire.com/post/2007/08/unixlinux-command-cheat-sheet/)
* [https://github.com/swcarpentry/boot-camps/blob/master/shell/shell_cheatsheet.md](https://github.com/swcarpentry/boot-camps/blob/master/shell/shell_cheatsheet.md)
* [tldr_ : Simplified version of the `man` pages (online and searchable)](https://tldr.ostera.io/)

Online tutorials:
* [Explain Shell](http://explainshell.com)
* [Introduction to the Command Line for Genomics](https://datacarpentry.org/shell-genomics/)
* [BASH Programming - Introduction HOW-TO](http://tldp.org/HOWTO/Bash-Prog-Intro-HOWTO.html)
* [Bioinformatics from the Command Line](https://medium.com/ngs-sh)

General help:
* Google it! - if you don't know how to do something, try Googling it, other people have probably had the same question.
* Learn by doing! There's no real other way to learn this than by trying it out.
  * Use vim on your laptop
  * Move around the directory structure on your laptop using the Terminal/Shell counts
  * Open folders and files using the command `open`
  * Automate something you don't really need to automate
* Use `man bash` to get more information about bash (bourne-again shell)

***
*These materials have been developed by members of the teaching team at the [Harvard Chan Bioinformatics Core (HBC)](http://bioinformatics.sph.harvard.edu/). These are open access materials distributed under the terms of the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0), which permits unrestricted use, distribution, and reproduction in any medium, provided the original author and source are credited.*

* *Some materials used in these lessons were derived from work that is Copyright © Data Carpentry (http://datacarpentry.org/). 
All Data Carpentry instructional material is made available under the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0).*

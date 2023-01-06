---
Week: "1" 
Lesson: "Intro to VACC & Command Line Part II"
Date: "Thursday, January 19, 2023"
---
# Starting Exercise: 
If you are able to complete the below tasks on your own, then you have successfully learned the lessons of Tuesday, January 17th. If not, please revisit the lesson titled **01_week1_mmg232.md**. All lessons will build upon each other therefore, it is crucial to keep up with the course content. 

+ Log-in to VACC-OOD and open terminal 
+ Navigate into `unix_lesson` folder 
+ List contents of `unix_lesson` folder 

***

# Learning Objectives for Today's Lesson
-  Understand the organization of the Filesystem 
- 
- 
- 

*** 
# Navigating the Filesystem
A filesystem organizes a computer's files and directories into a tree structure. 

<p align="center">
<img src="../img/directory_structure.png" width="600">
</p>

+ The first directory in the filesystem is the **root directory**. It is the parent of all other directories and files in the filesystem. That `/` or root is the 'top' level.
+ Each parent directory contains child directories and/or files. 
+ Each child directory can also contain more files

> Note: When you log in to a remote computer you land on one of the branches of that tree, i.e. your pre-designated "home" directory that usually has your login name as its name (e.g. `/users/username`).

To navigate the file system with ease we will now introduce **tab completion**. 

## Shortcut: Tab Completion
Typing out file or directory names can waste a lot of time and its easy to make typing mistakes. Instead we should get in the habbit of using tab complete as a shortcut. The `tab` key is located on the left side of your keyboard, right above the `caps lock` key. When you start typing out the first few characters of a directory name, then hit the `tab` key, Shell will try to fill in the rest of the directory name. Let's put this into practice now. 

## Exercise 
Navigate into the `raw_fastq` directory and see what's inside. **Remeber to use tab!**

```bash
$ cd raw_fastq/
```

Question: Where is `raw_fastq` in relation to our home directory?

## Paths 
To answer this, let's learn more about the "addresses" of directories, called **"path"** and move around the file system.

Let's check to see what directory we currently are in. The command prompt tells us which directory we are in, but it doesn't give information about where the `raw_fastq` directory is with respect to our "home" directory or the `/` directory.

The command to check our current location is `pwd`, this command does not take any arguments and it returns the path or address of your **p**resent **w**orking **d**irectory (the folder you are in currently).

```bash
$ pwd
```

<p align="center">
<img src="../img/pwd.png" width="600">
</p>

In the output above, each folder is separated from its "parent" or "child" folder by a "/", and the output starts with the root `/` directory. So, now you are able to determine the location of `raw_fastq` directory relative to the root directory. 

But what if you would like to navigate back to your home directory? No worries, just type `cd` and this will bring you back to your home directory. 

```bash
$ cd
```

After doing this what is your present working directory now?

```bash
$ pwd
```

It should look something like this: 
```
/users/p/d/pdrodrig
```

This should display a shorter string of directories starting with root. This is the full address to your home directory, also referred to as "**full path**". The "full" here refers to the fact that the path starts with the root, which means you know which branch of the tree you are on in reference to the root.


### Using paths with commands

You can do a lot more with the idea of stringing together *parent/child* directories. Let's say we want to look at the contents of the `raw_fastq` folder, but do it from our current directory (the home directory. We can use the list command and follow it up with the path to the folder we want to list!

```bash
$ cd

$ ls ~/unix_lesson/raw_fastq
```

```
Irrel_kd_1.subset.fq	Irrel_kd_3.subset.fq	Mov10_oe_2.subset.fq
Irrel_kd_2.subset.fq	Mov10_oe_1.subset.fq	Mov10_oe_3.subset.fq
```

Now, what if we wanted to change directories from `~` (home) to `raw_fastq` in a single step? 

```bash
$ cd ~/unix_lesson/raw_fastq
```
> Note: You can always copy-and-paste, but I do suggest typing it yourself to memorize the commands. 

Good job, you have moved 2 levels of directories with one command! 

Now, what if we want to move back up a level back into the `unix_lesson` directory?   
Type `cd unix_lesson` and see what happens.

*Unfortunately, that won't work because when you say `cd unix_lesson`, shell is looking for a folder called `unix_lesson` within your current directory, i.e. `raw_fastq`.*

Can you think of an alternative? 

+ You can use the full path to `unix_lesson`
+ You can do cd .. (allows you to move one folder up)

```bash
$ cd .. 
```

****

## File Names 
Probably one of the most frustrating parts of bioinformatics is the lack of consistency with how files are labeled. Files often have obsure names that is only relevant to the researcher, or have names that are **very** similar to each other. But nonetheless we will continue! 

Let's go into the `raw_fastq`, then type `ls Mov10_oe_`, followed by pressing the `tab` key once:

```bash
$ cd raw_fastq/
$ ls Mov10_oe_<tab>
```

**Nothing happens!!**

The reason is that there are multiple files in the `raw_fastq` directory that start with `Mov10_oe_`. As a result, shell does not know which one to fill in. When you hit `tab` a second time again, the shell will then list all the possible choices.

```bash
$ ls Mov10_oe_<tab><tab>

$ Mov10_oe_1.subset.fq  Mov10_oe_2.subset.fq  Mov10_oe_3.subset.fq
```


Now you can select the one you are interested in listed, and enter the number and hit tab again to fill in the complete name of the file.

```bash
$ ls Mov10_oe_1<tab>
```

> **NOTE:** Tab completion can also fill in the names of commands. For example, enter `e<tab><tab>`. You will see the name of every command that starts with an `e`. One of those is `echo`. If you enter `ech<tab>`, you will see that tab completion works. 

**Tab completion is your friend!** It helps prevent spelling mistakes, and speeds up the process of typing in the full command. We encourage you to use this when working on the command line. 

#### Relative paths

We have talked about **full** paths so far, but there is a way to specify paths to folders and files without having to worry about the root directory. And you have used this before when we were learning about the `cd` command.

Let's change directories back to our home directory, and once more change directories from `~` (home) to `raw_fastq` in a single step. (*Feel free to use your tab-completion to complete your path!*)

```bash
$ cd
$ cd unix_lesson/raw_fastq
```

This time we are not using the `~/` before `unix_lesson`. In this case we are using a relative path, relative to our current location - wherein we know that `unix_lesson` is a child folder in our home folder, and the `raw_fastq` folder is within `unix_lesson`.

> Previously we had used the following:
> ```bash
> $ cd ~/unix_lesson/raw_fastq
> ```

Remember there is also a handy shortcut for the relative path to a parent directory, 2 periods `..`. Let's say we wanted to move from the `raw_fastq` folder to its parent folder.

```bash
cd ..
```

You should now be in the `unix_lesson` directory (check command prompt or run `pwd`).

> You will be learning a little more about the `..` shortcut later. Can you think of an example when this shortcut to the parent directory won't work?
>
>   <details>
>     <summary>Answer</summary>
>     <P>When you are at the root directory, since there is no parent to the root directory!</P>
>   </details>

When using relative paths, you might need to check what the branches are downstream of the folder you are in. There is a really handy command (`tree`) that can help you see the structure of any directory.

```bash
$ tree
```

If you are aware of the directory structure, you can string together as long a list of directories as you like using either **relative** or **full** paths.

### Synopsis of Full versus Relative paths

**A full path always starts with a `/`, a relative path does not.**

A relative path is like getting directions from someone on the street. They tell you to "go right at the Stop sign, and then turn left on Main Street". That works great if you're standing there together, but not so well if you're trying to tell someone how to get there from another country. A full path is like GPS coordinates. It tells you exactly where something is no matter where you are right now.

You can usually use either a full path or a relative path depending on what is most convenient. If we are in the home directory, it is more convenient to just enter the relative path since it involves less typing.

Over time, it will become easier for you to keep a mental note of the structure of the directories that you are using and how to quickly navigate among them.

***

# Copying, creating, moving and removing data

Now we can move around within the directory structure using the command line. But what if we want to do things like copy files or move them from one directory to another, rename them? 

Let's move into the `raw_fastq` directory, this contains some fastq files which are the output of sequencing. 

```bash
cd ~/unix_lesson/raw_fastq
```

> **Tip** - These files are referred to as "raw" data since it has not been changed or analyzed after being generated.

### Copying

Let's use the copy (`cp`) command to make a copy of one of the files in this folder, `Mov10_oe_1.subset.fq`, and call the copied file `Mov10_oe_1.subset-copy.fq`. 
The copy command has the following syntax: 

`cp  path/to/item-being-copied  path/to/new-copied-item`

In this case the files are in our current directory, so we just have to specify the name of the file being copied, followed by whatever we want to call the newly copied file.

```bash
$ cp Mov10_oe_1.subset.fq Mov10_oe_1.subset-copy.fq

$ ls -l
```

The copy command can also be used for copying over whole directories, but the `-r` argument has to be added after the `cp` command. The `-r` stands for "recursively copy everything from the directory and its sub-directories". [We used it earlier when we copied over the `unix_lesson` directory to our home directories](#copying-example-data-folder).

### Creating

Next, let's create a directory called `fastq_backup` and we can move the copy of the fastq file into that directory. 

The `mkdir` command is used to make a directory, syntax: `mkdir  name-of-folder-to-be-created`.

```bash
$ mkdir fastq_backup
```

> **Tip** - File/directory/program names with spaces in them do not work well in Unix, use characters like hyphens or underscores instead. Using underscores instead of spaces is called "snake_case". Alternatively, some people choose to skip spaces and rather just capitalize the first letter of each new word (i.e. MyNewFile). This alternative technique is called "CamelCase".

### Moving

We can now move our copied fastq file in to the new directory. We can move files around using the move command, `mv`, syntax: 

`mv  path/to/item-being-moved  path/to/destination` 

In this case we can use relative paths and just type the name of the file and folder.

```bash
$ mv  Mov10_oe_1.subset-copy.fq  fastq_backup
```

Let's check if the move command worked like we wanted:

```bash
$ ls -l fastq_backup
```

### Renaming

The `mv` command has a second functionality, it is what you would use to rename files too. The syntax is identical to when we used `mv` for moving, but this time instead of giving a directory as its destination, we just give a new name as its destination. 

Let's try out this functionality!

The name Mov10_oe_1.subset-copy.fq is not very informative, we want to make sure that we have the word "backup" in it so we don't accidentally delete it.

```bash
$ cd fastq_backup

$ mv  Mov10_oe_1.subset-copy.fq   Mov10_oe_1.subset-backup.fq

$ ls
```

> **Tip** - You can use move to move a file and rename it at the same time!

**Important notes about `mv`**:
* When using `mv`, shell will **not** ask if you are sure that you want to "replace existing file" or similar unless you use the -i option. 
* Once replaced, it is not possible to get the replaced file back!

### Removing

We find out that we did not need to create backups of our fastq files manually as backups were generated by our collaborator; in the interest of saving space on the cluster, we want to delete the contents of the `fastq-backup` folder and the folder itself. 

```bash
$ rm  Mov10_oe_1.subset-backup.fq
```

Important notes about `rm`
* `rm` permanently removes/deletes the file/folder. 
* There is no concept of "Trash" or "Recycle Bin" on the command-line. When you use `rm` to remove/delete they're really gone. 
* **Be careful with this command!**
* You can use the `-i` argument if you want it to ask before removing, `rm -i file-name`.

Let's delete the fastq_backup folder too. First, we'll have to navigate our way to the parent directory (we can't delete the folder we are currently in/using). 

```bash
$ cd ..

$ rm  fastq_backup 
```

Did that work? Did you get an error?

<details>
  <summary><i>Explanation</i></summary>
  <P>By default, <code>rm</code>, will NOT delete directories, but you use the <code>-r</code> flag if you are sure that you want to delete the directories and everything within them. To be safe, let's use it with the <code>-i</code> flag.</P>
</details><br>

```bash
$ rm -ri fastq_backup
```

- `-r`: recursive, commonly used as an option when working with directories, e.g. with `cp`. 
- `-i`: prompt before every removal.

***

**Exercise**

1. Create a new folder in `unix_lesson` called `selected_fastq`
2. Copy over the Irrel_kd_2.subset.fq and Mov10_oe_2.subset.fq from `raw_fastq` to the `~/unix_lesson/selected_fastq` folder
3. Rename the `selected_fastq` folder and call it `exercise1`

***

## Exiting from the cluster

To close the interactive session on the cluser as well as to disconnect from the cluster, the command is `exit`. So, you are going to have to run the exit command twice.

```
[rc_training01@compute-a-16-166 ~]$ exit
[rc_training01@login04 ~]$ exit
logout
Connection to o2.hms.harvard.edu closed.
HSPH-Radhikas-MacBook-Pro:~ rsk394$ 
```

*** 
## Commands

```
cd          # Change Directory
               +   used to move throughout the filesystem of a computer 

ls          # List 
              +   list the contents of a directory

pwd         # Print Working Directory   
              +  displays the file path from the root directory to the current working directory 

tree        # prints a tree of the file structure

cp          # Copy
              +   used to copy files or directories 

mkdir       # Make Directory
              +   used to make a new directory 

mv          # Move 
              +   move a file into a directory 

rm          # Remove
              +   used to delete files and directories 
```

## Shortcuts

```
~           # home directory
.           # current directory
..          # navigate into the parent directory of the current directory 
```

*** 
# Homework Assignment #1 


---

## Citation
*This lesson has been developed by members of the teaching team at the [Harvard Chan Bioinformatics Core (HBC)](http://bioinformatics.sph.harvard.edu/). These are open access materials distributed under the terms of the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0), which permits unrestricted use, distribution, and reproduction in any medium, provided the original author and source are credited.*

* *The materials used in this lesson were derived from work that is Copyright © Data Carpentry (http://datacarpentry.org/). 
All Data Carpentry instructional material is made available under the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0).*
* *Adapted from the lesson by Tracy Teal. Original contributors: Paul Wilson, Milad Fatenejad, Sasha Wood and Radhika Khetani for Software Carpentry (http://software-carpentry.org/)*
*authors: Sheldon  McKay, Mary Piper, Radhika Khetani, Meeta Mistry, Jihe Liu*
*date posted: September 28, 2020*

*Other parts of this lesson were derived from:*  
Erin Alison Becker, Anita Schürch, Tracy Teal, Sheldon John McKay, Jessica Elizabeth Mizzi, 
François Michonneau, et al. (2019, June). datacarpentry/shell-genomics: Data Carpentry: Introduction to the shell for genomics data, 
June 2019 (Version v2019.06.1). Zenodo. http://doi.org/10.5281/zenodo.3260560

---
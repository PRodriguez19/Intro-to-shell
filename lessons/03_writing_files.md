---
Week: "2" 
Lesson: "Writing and editing files"
Date: "Thursday, January 26, 2023"
---

# Learning Objectives
  - Implement tab completion when writing paths
  - Use of the asterisk `*` wildcard to select multiple items
  - List a few shortcuts 
  - View the contents of a file

***

# Writing files

We've been able to do a lot of work with files that already exist, but what if we want to write and/or create our own files? Obviously, we're not going to type in sequence information for a FASTA file, but you'll see as we go that there are a lot of situations in which we would need to write/create a file or edit an existing file.

In order to create or edit files we will need to use a **text editor**. When we say, "text editor," we really do mean "text": these editors can only work with plain character data, not tables, images, or any other media. The types of text editors available can generally be grouped into two categories: **graphical user interface (GUI) text editors** and **command-line editors**.

### GUI text editors

A GUI is an interface that has buttons and menus that you can click on to issue commands to the computer and you can move about the interface just by pointing and clicking. You might be familar with GUI text editors, such as [BBEdit](http://www.barebones.com/products/bbedit/), [Sublime](http://www.sublimetext.com/), [Visual Studio Code](https://code.visualstudio.com/) and [Notepad++](http://notepad-plus-plus.org/), which allow you to write and edit plain text documents. These editors often have features to easily search text, extract text, and highlight syntax from multiple programming languages. They are great tools, but since they are 'point-and-click', we cannot efficiently use them from the command line.

### Command-line editors

When working remotely, we need a text editor that functions from the command line interface. With command-line editors you must navigate the interface using the arrow keys and shortcuts, since you do not have the option to 'point-and-click'. Some popular editors include [Emacs](http://www.gnu.org/software/emacs/), [Vim](http://www.vim.org/), or a graphical editor such as [Gedit](http://projects.gnome.org/gedit/). These are editors which are generally available for use on high-performance compute clusters. There are also simpler editors available for use on the cluster (e.g. [nano](http://www.nano-editor.org/)), but tend to have limited functionality.

### Introduction to Vim 

To write and edit files, we're going to use a text editor called 'Vim'. Vim is a very powerful text editor, and it offers extensive text editing options. However, in this introduction we are going to focus on **exploring some of the more basic functions**. 

> #### How do I keep track of all these shortcuts in Vim?
> To help you remember some of the keyboard shortcuts that are introduced below and to allow you to explore additional functionality on your own, we have compiled a [cheatsheet linked here](https://github.com/hbctraining/In-depth-NGS-Data-Analysis-Course/blob/master/resources/VI_CommandReference.pdf). Download it to your computer, it is a useful resource to have open while using Vim.
> <p align="center">
> <img src="../img/vim_cheatsheet.png" width="600">
> </p>


### Vim Interface

You can create a document by calling a text editor (in our case `vim`) and providing the name of the document you wish to create. 

Change directories to the `~/unix_lesson/other` folder and create a document using called `draft.txt` using the `vim` command:

```bash
$ cd ~/unix_lesson/other
	
$ vim draft.txt
```

**Note the `"draft.txt" [New File]` typed at the bottom left-hand section of the screen.** This tells you that you just created a new file in vim. 


### Vim Modes
Vim has **_two basic modes_** that will allow you to create documents and edit your text:   

- **_command mode (default mode):_** will allow you to save and quit the program (and execute other more advanced commands).  

- **_insert (or edit) mode:_** will allow you to write and edit text


Upon creation of a file, vim is automatically in command mode. Let's _change to insert mode_ by typing <kbd>i</kbd>. **Note the `--INSERT--` at the bottom left hand of the screen.** Now type in a few lines of text:

<p align="center">
<img src="../img/vim_insert.png" width="600">
</p>

After you have finished typing, **press <kbd>esc</kbd> to enter command mode.** 

**Note the `--INSERT--` has now disappeared from the bottom of the screen.**

> ### Review of Vim modes
> 
> | key              | action                 |
> | ---------------- | ---------------------- |
> | <button>i</button>     | insert mode - to write and edit text |
> | <button>esc</button>     | command mode - to issue commands / shortcuts  |
> 


### Saving and Quitting

To **"write to file"** or save the modifications made to the file, **type <kbd>:w</kbd>** when in command mode. You can see the commands you type in the bottom left-hand corner of the screen. 

<p align="center">
<img src="../img/vim_save.png" width="600">
</p>

After you have saved the file, the total number of lines and characters in the file will print out at the bottom left-hand section of the screen.

<p align="center">
<img src="../img/vim_postsave.png" width="600">
</p>


Alternatively, we can **write to file (save changes) and quit** all at once by **typing <kbd>:wq</kbd>**. Now, you should have exited vim and returned back to your command prompt.

To edit the newly created `draft.txt` file, you can open it again with vim: `vim draft.txt`. First, change to *insert mode* and type a few additional lines (you can move around the lines using the arrows on the keyboard). This time we decide to **quit without saving** by going into command mode by pressing the <button>esc</button> key, and then **typing <kbd>:q!</kbd>**.
 
<p align="center">
<img src="../img/vim_quit.png" width="600">
</p>


> ### Review of saving and quitting
> 
> | key (in command mode)  | action           |
> | ---------------- | ---------------------- |
> | <button>:w</button>     | to write to file (save) |
> | <button>:wq</button>     | to write to file and quit |
> | <button>:q!</button>     | to quit without saving |


### Shortcuts in Vim

While we cannot point and click to navigate the document, we can use the arrow keys to move around. However, navigating with arrow keys can be very slow, so Vim has shortcuts (which are completely unintuitive, but very useful as you get used to them over time). 

Create a new file called `spider.txt` using `vim`. Go into *insert mode* and enter the text as shown below in the screenshot: 

<p align="center">
<img src="../img/vim_spider.png" width="600">
</p>

Once you have finished typing, you can display line numbers by changing to *command mode* and then typing the <kbd>:set number</kbd> command. Later, if you choose to remove the line numbers you can reset it with <kbd>:set nonumber</kbd>.

<p align="center">
<img src="../img/vim_spider_number.png" width="600">
</p>

| key (in command mode)  | action                 |
| ---------------- | ---------------------- |
| <button>:set number</button>     | to number lines |
| <button>:set nonumber</button>     | to remove line numbers    |


**Save the document.** Check to see what mode you are currently in. **While in command mode**, try moving around the file `spider.txt` and familarizing yourself with some of these shortcuts!  

**Navigating around the file**

| key (in command mode) | action                 |
| ---------------- | ---------------------- |
| <button>gg</button>     | to move to top of file |
| <button>G</button>     | to move to bottom of file     |
| <button>$</button>     | to move to end of line |
| <button>0</button>     | to move to beginning of line     |
| <button>w</button>     | to move to next word     |
| <button>b</button>     | to move to previous word     |

Practice some of the editing shortcuts, then **quit the document without saving any changes**.

**Editing the file**

| key (in command mode) | action                 |
| ---------------- | ---------------------- |
| <button>dw</button>     | to delete word |
| <button>dd</button>     | to delete line     |
| <button>u</button>     | to undo |
| <button>Ctrl + r</button>     | to redo     |
| <button>/*pattern*</button>     | to search for a pattern (*n/N* to move to next/previous match)    |
| <button>:%s/*search*/*replace*/g</button>     | to search for a pattern and replace for all occurences     |


*** 

**Exercise**

We have covered some basic commands in vim, but practice is key for getting comfortable with the program. Let's
practice what we just learned in a brief challenge.

1. Open `spider.txt`, and delete the word "water" from line #2.
2. Quit without saving.
3. Open `spider.txt` again, and replace every occurrence of "spider" with "unicorn".
4. Delete: "Down came the rain." 
5. Save the file.
6. Undo your previous deletion.
7. Redo your previous deletion.
8. Delete the first and last words from each of the lines.
9. Save the file.
10. Open up the file and copy and paste the contents to a text editor on your local laptop to submit as homework.
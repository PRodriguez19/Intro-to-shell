---
Week: "2" 
Lesson: "Working with files on the command-line"
Date: "Tuesday, January 24, 2023"
---

## Learning Objectives

- View the contents of a file

## Examining Files

We now know how to move around the file system and look at the contents of directories, but how do we look at the contents of files? On your laptop, to view a file all you need to do is double click it to open it. What is the command-line version of this? Let's explore a few commands.  

### `cat` command

The easiest way to examine a file is to just print out all of its contents using the command `cat`. We can test this out by printing the contents of `~/unix_lesson/other/sequences.fa`. Enter the command followed by the filename, including the path when necessary:

```bash
$ cat ~/unix_lesson/other/sequences.fa
```

The `cat` command prints out the all the contents of `sequences.fa` to the screen.

> `cat` stands for catenate; it has many uses and printing the contents of a files onto the terminal is one of them.

**What does this file contain?**

```bash

>SRR014849.1 EIXKN4201CFU84 length=93 
GGGGGGGGGGGGGGGGCTTTTTTTGTTTGGAACCGAAAGGGTTTTGAATTTCAAACCCTTTTCGGTTTCCAACCTTCCAAAGCAATGCCAATA

>gi|340780744|ref|NC_015850.1| Acidithiobacillus caldus SM-1 chromosome, complete genome
ATGAGTAGTCATTCAGCGCCGACAGCGTTGCAAGATGGAGCCGCGCTGTGGTCCGCCCTATGCGTCCAACTGGAGCTCGTCACGAG
TCCGCAGCAGTTCAATACCTGGCTGCGGCCCCTGCGTGGCGAATTGCAGGGTCATGAGCTGCGCCTGCTCGCCCCCAATCCCTTCG
TCCGCGACTGGGTGCGTGAACGCATGGCCGAACTCGTCAAGGAACAGCTGCAGCGGATCGCTCCGGGTTTTGAGCTGGTCTTCGCT
CTGGACGAAGAGGCAGCAGCGGCGACATCGGCACCGACCGCGAGCATTGCGCCCGAGCGCAGCAGCGCACCCGGTGGTCACCGCCT
CAACCCAGCCTTCAACTTCCAGTCCTACGTCGAAGGGAAGTCCAATCAGCTCGCCCTGGCGGCAGCCCGCCAGGTTGCCCAGCATC
CAGGCAAATCCTACAACCCACTGTACATTTATGGTGGTGTGGGCCTCGGCAAGACGCACCTCATGCAGGCCGTGGGCAACGATATC
CTGCAGCGGCAACCCGAGGCCAAGGTGCTCTATATCAGCTCCGAAGGCTTCATCATGGATATGGTGCGCTCGCTGCAACACAATAC
CATCAACGACTTCAAACAGCGTTATCGCAAGCTGGACGCCCTGCTCATCGACGACATCCAGTTCTTTGCGGGCAAGGACCGCACCC

>gi|129295|sp|P01013|OVAX_CHICK GENE X PROTEIN (OVALBUMIN-RELATED)
QIKDLLVSSSTDLDTTLVLVNAIYFKGMWKTAFNAEDTREMPFHVTKQESKPVQMMCMNNSFNVATLPAE

```

Question: What command would I use to clear my terminal screen? 

<details>
      <summary><b><i>Answer</i></b></summary>
      <p><br><button>Ctrl</button> + <button>L</button> </p>
</details>  

### `less` command

`cat` is a terrific command, but when the file is really big, it can be annoying to use. In practice, when you are running your analyses on the command-line you will most likely be dealing with large files. In our case, we have FASTQ files. Let's take a look at the list of raw_fastq files and add the `-h` modifier to see how big the files are. 

```bash
$ ls -lh ~/unix_lesson/raw_fastq
```

> The `ls` command has a modifier `-h` when paired with `-l`, will list the files and also print sizes of files in human readable format. 

In the fourth column you wll see the size of each of these files, and you can see they are quite large, so we probably do not want to use the `cat` command to look at them. Instead, we can use the `less` command. 

Move into our `raw_fastq` directory and enter the following command:

```bash
$ less Mov10_oe_1.subset.fq
```
Rather than printing to screen, the `less` command opens the file in a new buffer allowing you to navigate through it. Does this look familiar? You might remember encountering a similar interface when you used the `man` command. This is because `man` is using the `less` command to open up the documentation files! The keys used to move around the file are identical to the `man` command. Below we have listed some additional shortcut keys for naviagting through your file when using `less`.

<span class="caption">Shortcuts for `less`</span>

| key              | action                 |
| ---------------- | ---------------------- |
| <kbd>SPACE</kbd> | to go forward          |
| <kbd>b</kbd>     | to go backwards        |
| <kbd>g</kbd>     | to go to the beginning |
| <kbd>G</kbd>     | to go to the end       |
| <kbd>q</kbd>     | to quit                |


Use the shortcut keys to move through your FASTQ file, we will explore these files in more detail later in the workshop. 

#### Searching files with `less`

`less` also gives you a way of searching through files. 

Just type in <kbd>/</kbd> to begin a search, you will see that the `/` will show up at the  bottom of the `less` buffer. Let's say you are interested in searching for the following 8-letter adapter sequence: 

```
/GGCGAATT
```

Enter the name of the string of characters you would like to search for and hit the enter key. The interface will move to show you the location where that string is found, and highlight the string. 

If you hit <kbd>/</kbd> then <kbd>ENTER</kbd>, `less` will just repeat the previous search. 

`less` searches from the current location and works its way forward. For instance, the sequence `GGCGAATT` was found in our file, but if we started the search at the end of the file, `less` will not find it. You need to go to the beginning of the file and search.

To exit hit <kbd>q</kbd>. 

### `head` and `tail` commands

There's another way that we can look at files, and just look at part of them. In particular, if we just want to see the beginning or end of the file to see how it's formatted.

The commands are `head` and `tail` and they just let you look at the beginning and end of a file respectively.

```bash
$ head Mov10_oe_1.subset.fq
```

```bash
$ tail Mov10_oe_1.subset.fq
```

By default, the first or last 10 lines will be printed to screen. The `-n` option can be used with either of these commands to specify the number `n` lines of a file to display. For example, let's print the first/last line of the file:

```bash
$ head -n 1 Mov10_oe_1.subset.fq

$ tail -n 1 Mov10_oe_1.subset.fq
```

*** 

**Exercise**

1. Change directories into `genomics_data`. You can do this using a full or relative path.
2. Use the `less` command to open up the file `Encode-hesc-Nanog.bed`.
3. Search for the string `chr11`; you'll see all instances in the file highlighted.
4. Staying in the `less` buffer, use the shortcut to get to the end of the file. Report the three highlighted lines at the end of the file where you see `chr11` highlighted. 
5. Exit the `less` buffer and come back to the command prompt.
6. Print to screen the last 5 lines of the file `Encode-hesc-Nanog.bed`. Report what you see as the output within the Terminal.

---

*This lesson has been developed by members of the teaching team at the [Harvard Chan Bioinformatics Core (HBC)](http://bioinformatics.sph.harvard.edu/). These are open access materials distributed under the terms of the [Creative Commons Attribution license](https://creativecommons.org/licenses/by/4.0/) (CC BY 4.0), which permits unrestricted use, distribution, and reproduction in any medium, provided the original author and source are credited.*

# Learn command line

Please follow and complete the free online [Bash Scripting Tutorial](https://ryanstutorials.net/bash-scripting-tutorial/) or [Codecademy's Learn the Command Line](https://www.codecademy.com/learn/learn-the-command-line). These are helpful tutorials. You should be able to go through these in a couple of hours.

**Note:** Bash is not installed on a PC. Rather, PC users must install Cygwin. Once Cygwin has been installed, the command line interface witll _emulate_ bash. You can find all information regarding Cygwin [here](https://www.cygwin.com/).

---

### Q1.  Cheat Sheet of Commands  

Here's a list of items with which you should be familiar:  
* show current working directory path
* creating a directory
* deleting a directory
* creating a file using `touch` command
* deleting a file
* renaming a file
* listing hidden files
* copying a file from one directory to another

Make a cheat sheet for yourself: a list of at least **ten** commands and what they do.  (Use the 8 items above and add a couple of your own.)  

* `rm -rf dirname` - delete a directory
* `mkdir dirname` - create a directory
* `touch filename` - create a file
* `mv file1 file2` - rename a file
* `ls -a` - list hidden files
* `cp dir1/file1 dir2/file1` - copy a file from one directory to another
* `pwd` - show current working directory path
* `rm -i filename` - delete a file
* `sudo !!` - repeat last command with sudo
* `ps aux | grep task` - list and aux task  
* `sudo echo "make me a sandwhich"` - command someone to make you a sandwhich ([xkcd reference](https://xkcd.com/149/))

---

### Q2.  List Files in Unix   

What do the following commands do:  
`ls` - list all files (in a directory)  
`ls -a`  - ... + hidden files  
`ls -l`  - ... in a column with meta data  
`ls -lh` - ... in a column with meta data and human readable sizes  
`ls -lah`- ... in a column with meta data and human readable sizes and   hidden files  
`ls -t`  - ... sort by time (last modified)  
`ls -Glp` - ... in a column with / after dir name and colorize output  


---

### Q3.  More List Files in Unix  

Explore these other [ls options](http://www.techonthenet.com/unix/basic/ls.php) and pick 5 of your favorites:

`ls -l --time-style=full-iso` - print time as iso format  
`ls --sort=extension` - sort files by extension type  
`ls -tr` - sort files in reverse order last modification time  
`ls -n` - show UID/ GID  
`ls -1` - show each entry on one line


---

### Q4.  Xargs   

What does `xargs` do? Give an example of how to use it.

xargs helps other commands accept standard input (STIN) as arguments.

the following example finds files named untitled.txt and removes them.

`find ./ -type f -name "untitled.txt" | xargs rm`
 

the first part of the command (before the pipe) finds the files. 
`find ./ -type f -name "untitled.txt"`  

the second part (after the pipe) handles and breaks up the standard input and passes it to the remove command.   
`xargs rm`
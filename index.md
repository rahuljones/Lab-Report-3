# Lab Report 3

**Finding and Removing Files**

Source: [https://www.geeksforgeeks.org/find-command-in-linux-with-examples](https://www.geeksforgeeks.org/find-command-in-linux-with-examples)
```
[cs15lwi23avo@ieng6-201]:OUP:515$ cd Berk
[cs15lwi23avo@ieng6-201]:Berk:516$ ls
CH4.txt  ch1.txt  ch2.txt  ch7.txt
[cs15lwi23avo@ieng6-201]:Berk:517$ find . -type f -name "ch7.txt" -exec rm -f {} \;
[cs15lwi23avo@ieng6-201]:Berk:518$ ls
CH4.txt  ch1.txt  ch2.txt
```
This command works by finding the file using the name of the file and then using the remove command to remove it from the directory. It would be useful when you are trying to remove a file from a directory, but you don't exactly know where it is.

```
[cs15lwi23avo@ieng6-201]:Berk:518$ ls
CH4.txt  ch1.txt  ch2.txt
[cs15lwi23avo@ieng6-201]:Berk:519$ find . -type f -name "fileThatDoesntExist.txt" -exec rm -f {} \;
[cs15lwi23avo@ieng6-201]:Berk:520$ ls
CH4.txt  ch1.txt  ch2.txt
```
Again the command is searching for the file to delete it, but because the file does not exist in the directory, nothing is deleted.

**Finding Empty Files**

[https://www.tecmint.com/35-practical-examples-of-linux-find-command](https://www.tecmint.com/35-practical-examples-of-linux-find-command)
```
[cs15lwi23avo@ieng6-201]:Berk:527$ find -empty       
[cs15lwi23avo@ieng6-201]:Berk:528$      
```
This command searches for empty files or directories. Since none were found in this directory, the command did not change anything in the directory.
```
[cs15lwi23avo@ieng6-201]:Berk:528$ mkdir empty
[cs15lwi23avo@ieng6-201]:Berk:529$ ls
CH4.txt  ch1.txt  ch2.txt  empty
[cs15lwi23avo@ieng6-201]:Berk:530$ find -empty
./empty
[cs15lwi23avo@ieng6-201]:Berk:531$ 
```
Here the command finds an empty directory and returns the path to the directory when it is executed. This would be useful to seeing which files and directories are empty in your computer.

**Finding Files with Size**

Source:[https://www.tecmint.com/35-practical-examples-of-linux-find-command/](https://www.tecmint.com/35-practical-examples-of-linux-find-command)
```
[cs15lwi23avo@ieng6-201]:OUP:534$ find Berk/ -size 1M 
Berk/
Berk/CH4.txt
Berk/ch1.txt
Berk/ch2.txt
Berk/empty
[cs15lwi23avo@ieng6-201]:OUP:535$
```
This command finds all of the files with a size of 1 megabyte. This command would be useful for trying to find files of a certain size or trying to find the largest file in a directory.
```
[cs15lwi23avo@ieng6-201]:OUP:535$ find Berk/ -size 50M
[cs15lwi23avo@ieng6-201]:OUP:536$ 
```
Here the command runs, but there are no files that have a size of 50 megabytes, so there are no files that are returned.

**Finding Files Without Exact Name**

Source: [https://www.redhat.com/sysadmin/linux-find-command](https://www.redhat.com/sysadmin/linux-find-command)
```
[cs15lwi23avo@ieng6-201]:OUP:541$ find Berk/ -iname "*ch4*txt" 2>/dev/null
Berk/CH4.txt
[cs15lwi23avo@ieng6-201]:OUP:542$
```
Even though the exact capitalization was not used in this case, the find command was still able to get the path to the file. This would be very useful if you cannot exactly remember the capitalization of your file name, and you want to find the file.
```
[cs15lwi23avo@ieng6-201]:OUP:558$ find Berk/ -iname "*ch2*txt" 2>/dev/null
Berk/ch2.txt
[cs15lwi23avo@ieng6-201]:OUP:559$ 
```
Here we can see how the command also works when the exact file name is used.

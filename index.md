# Lab Report 2

**Finding and Removing Files**

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

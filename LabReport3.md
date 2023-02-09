# cse15l-lab-reports
# LabReport 3

I choose the ``grep`` command

``grep`` command is used to **search** a file with particular **pattern**

The most coomand option can be find on <https://www.geeksforgeeks.org/grep-command-in-unixlinux/>

### -l option

``-l`` display the list of **filename** rather than the lines that contain the pattern

````terminal
grep -l pattern <<fileName>>
````

In this picture, I am finding the word "Vista" in the 

### -h option

``-h`` option displays the **matched lines** that contain the pattern without displaying the filename of the content

````terminal
grep -h pattern <<fileName>>
````



### -c option

``-c`` command prints out the **number** of lines that contain the specified pattern

``````terminal
grep -c pattern <<fileName>>
``````



### -w option

``-w`` helps math the whole word rather than the word that partly contains the pattern

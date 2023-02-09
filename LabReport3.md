# cse15l-lab-reports
# LabReport 3

I choose the ``grep`` command

``grep`` command is used to **search** a file with particular **pattern**

The most coomand option can be find on <https://www.geeksforgeeks.org/grep-command-in-unixlinux/>

### -l option

``-l`` display the list of **filename** rather than the lines that contain the pattern

````terminal
grep -l pattern <<fileName>>
```<img width="568" alt="截屏2023-02-09 下午1 27 40" src="https://user-images.githubusercontent.com/114774291/217943971-862df8d9-fb1d-4bd4-aa50-b4a4b7ef6932.png">
`
<img width="760" alt="截屏2023-02-09 下午1 29 33" src="https://user-images.githubusercontent.com/114774291/217943990-e4525d14-9549-4b18-aa4e-54fab4d0b8ac.png">

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


````terminal
grep -w pattern <<fileName>>
````



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
<img width="568" alt="截屏2023-02-09 下午1 27 40" src="https://user-images.githubusercontent.com/114774291/217943971-862df8d9-fb1d-4bd4-aa50-b4a4b7ef6932.png">
In this picture, I am finding the word "Vista" in the realtive path ``written_2/travel_guides/berlitz1/*.txt`` and you can see in the result that it only listed the file names rather than the lines that contain the pattern
<img width="760" alt="截屏2023-02-09 下午1 29 33" src="https://user-images.githubusercontent.com/114774291/217943990-e4525d14-9549-4b18-aa4e-54fab4d0b8ac.png">
In this picture, I am finding the word "Vista" in the realtive path ``written_2/travel_guides/berlitz2/*.txt`` and you can see in the result that it only listed the **file names** rather than the lines that contain the pattern.

### -h option

``-h`` option displays the **matched lines** that contain the pattern without displaying the filename of the content

````terminal
grep -h pattern <<fileName>>
````
<img width="570" alt="截屏2023-02-09 下午1 38 56" src="https://user-images.githubusercontent.com/114774291/217946304-1419c2ad-d235-41cb-b239-128d1dd78e7b.png">
In this picture, we are trying the option ``-h`` and we can see that it printed out all the **matched lines** with the pattern without printing out the filename.
<img width="571" alt="截屏2023-02-09 下午1 48 11" src="https://user-images.githubusercontent.com/114774291/217947385-d5af4e8b-5fa5-4152-beb5-b9cbeaacd62e.png">
In this picture, we are trying another specified pattern ``Rocha``, and we can see that, as we expected, it prints out the lines that contained the specified pattern


### -c option

``-c`` command prints out the **number** of lines that contain the specified pattern

``````terminal
grep -c pattern <<fileName>>
``````
<img width="567" alt="截屏2023-02-09 下午1 40 05" src="https://user-images.githubusercontent.com/114774291/217946344-ea902b66-066a-46b4-8af0-b2eaa3c16ad6.png">
In this picture we are trying out the ``-c`` option. We can see that it listed all the files in the given relative path and showed the number of matching patterns within the file. For instance, we can see that in ``WhereToGo.txt``, there is 1 matching, which is consistance with the result when we are trying the "-l" command for the same realtive path.
<img width="571" alt="截屏2023-02-09 下午1 47 34" src="https://user-images.githubusercontent.com/114774291/217947345-df99967a-ad50-4764-a1f6-aafda0574cac.png">
In this picture, we are trying out the ``-c`` command with another specified pattern ``Rocha`` and we can see that it prints out the number of occurance of the word for Rocha in each ``.txt`` file


### -w option

``-w`` helps math the whole word rather than the word that partly contains the pattern


````terminal
grep -w pattern <<fileName>>
````



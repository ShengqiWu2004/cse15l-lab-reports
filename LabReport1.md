# cse15l-lab-reports
#### Task1: Installing VScode

First, go to <https://code.visualstudio.com/> ,and select the version that fits your computer!
<img width="958" alt="截屏2023-01-12 下午1 17 27" src="https://user-images.githubusercontent.com/114774291/212183291-84968983-3280-4538-af9f-eb37f1cdd8a2.png">

#### Task2: Remotely Control

First you should open the terminal on the MacBook, and copy the command down here, remember to change zz to your specific 15L account, then the thing will be shown like the following picture.
```terminal
$ ssh cs15lwi23zz@ieng6.ucsd.edu
```
<img width="964" alt="截屏2023-01-12 下午1 17 34" src="https://user-images.githubusercontent.com/114774291/212183342-8e9bb226-937e-4e37-809b-4ebd840002ef.png">


Second, type **yes** and then you will get to the step that requires you to enter the password.

<img width="957" alt="截屏2023-01-12 下午1 17 42" src="https://user-images.githubusercontent.com/114774291/212183429-bbecd516-ef91-470b-8f67-f60b97ddcae1.png">

When you are entering the password, the password is not shown in the terminal for security reasons. You may need to go to <https://sdacs.ucsd.edu/~icc/index.php> to view your own account and change the password. When changing, you need to press Enter instead of the button "Check Password."

After successfully entered the password, the terminal should look like the picture below

<img width="948" alt="截屏2023-01-12 下午1 17 52" src="https://user-images.githubusercontent.com/114774291/212183542-ba042584-ef9f-43ae-ba05-ded62892adfc.png">

#### Task 3: Trying Some Commands


```terminal
cd
```

The command "cd" means change directory.
``cd``takes in the path to the specific directory, which includes relative path and absolute path.
For instance, you can try out the cd command with ``cd ~`` or ``cd ..``, where "~" means home directory and ".." means the previous folder

```
ls<path>
```

"List" Used to list the files and folders the given path. Thus, ls <home/linux/ieng6/cs15lwi23/cs15lwi23ahr> means listing all the folders and files in the given path.
You can check out <https://www.inmotionhosting.com/support/server/linux/ls-command/> for more specific ls commands
-	Indicates a file does not have extended security information. And 

```
cp
```

Cp means making a copy of the file.
cp “filename” “newfilename” this command copies the content in the "filename" into a new file called "newfilename"

```
cat <path1><path2>
```

"Concatenate" Used to print the contents of one or more files given by the paths
The following picture is the screenshot for most of the commands

<img width="961" alt="截屏2023-01-12 下午1 17 59" src="https://user-images.githubusercontent.com/114774291/212183670-5c8707eb-c506-4a9f-9860-21bdd2c66a99.png">

In this specific case ``ls -a`` lists all the files and documents in the current directory, including hidden file. "-a" means all.
``-t`` means listing the file chronologically rather than according to the filename.    ``-l``means listing the detailed information of the file.
Thus ``ls -lat`` together means list the detailed information off all the files in the current directory chronologically.

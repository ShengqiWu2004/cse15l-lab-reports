# Lab Report 4

#### Step 1: **Setup** 

##### **Setup** Delete any existing forks of the repository you have on your account

You should delete each repository seperately. First click on the title of the repository. For instance, ``lab3`` and then click on <Setting> and then scroll down to see the button <Delete this respository> and then type down the line to confirm deletion.

#### Step 2: Setup

##### Fork the repository

You should first click on the link for the repository <https://github.com/ucsd-cse15l-w23/lab7> and then click on the button <fork> and then click on the button <create fork> to confirm forking the respository.

#### Step 3: The real Deal

##### Start the timer!

#### Step 4

##### Log into ieng6

Key Pressed: `<Command C><Command V><enter>`

After copy and paste the ``ssh cs15lwi23ahr@ieng6.ucsd.edu`` command, it will log into the ieng6 account and there will be no more prompt for ssh key because we have just authorized to skip the process. We can store the ssh command previously in a notebook to speed up!

#### Step 5

##### Clone your fork of the repository from your Github account

Key Pressed: `<Command C><Command V><enter>`

We could pre-save the url for your own fork of repository <[git@github.com](mailto:git@github.com):ShengqiWu2004/lab7.git> so when doing the tournament, we only need to copy and paste. It will increase out speed.

#### Step 6

##### Run the tests, demonstrating that they fail

Key pressed: `cd l<tab>` ,` <Command C><Command V><enter>`, `<Command C><Command V><enter>`

First, we should use `cd lab7/` to change our current directory to the directory lab7 ``<Tab>`` will autofill ``lab7/`` for us. Since I stored the`` javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`` for compiling Junit and ``java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples`` for running Junit in a notebook, I could only press `<Comand C><Command V><enter>` to achieve the goal.



#### Step 7

##### Edit the code file to fix the failing test

Key Pressed: `nano L<tab>java<enter>`, `<down><right><delete><delete>`,`<down><left><delete>2`,` <Control O><enter><Control X>`

First, we should use ``nano ListExamples.java`` to take a look at ListExamples.java and then dele the ``0,`` and change the last appearance of ``index1`` to ``index2``. Then we should press `<Control O>` and ``enter``to save the changes. and press `<Control X> ` to exit the page. 

#### Step 8

##### Run the tests, demonstrating that they now succeed

Key Pressed:` <up><up><up><enter>`,`<up><up><up><enter>`

The ``javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java`` command was 3 up in the search history, so I used up arrow to access it. Then the ``java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore TestListExamples`` command was 3 up in the history, so I accessed and ran it. 

#### Step 9

##### Commit and push the resulting change to your Github account

Key Pressed: `git add L<tab>java<enter>`, `git com<tab> -m "Updated"<enter>`, `git push o<tab> m<tab><enter>`

We could use ``git add `` to store the changes we just made to ``ListExamples.java``. We can use `<Tab>` to autofill the name of the file so that we will save some time.

Then we could use ``git commit -m`` to commit our changes to the repository. We could use the ``com<Tab>`` to autofill for the command ``commit``

Then we could use the command ``git push original main`` to push our commitment to the repository. We could use `<Tab>` to fill for ``original`` and ``main`` to save some time.

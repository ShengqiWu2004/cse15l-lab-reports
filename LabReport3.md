# cse15l-lab-reports
# LabReport 3

I choose the ``grep`` command

``grep`` command is used to **search** a file with particular **pattern**


### -l option

``-l`` display the list of **filename** rather than the lines that contain the pattern

``````terminal
grep -l pattern <<fileName>>
``````
``````terminal
wushengqi@wushengqideMacBook-Pro docsearch-main % grep -l "vista" written_2/travel_guides/berlitz1/*.txt
written_2/travel_guides/berlitz1/IntroDublin.txt
written_2/travel_guides/berlitz1/IntroLakeDistrict.txt
written_2/travel_guides/berlitz1/IntroMadeira.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToGreek.txt
written_2/travel_guides/berlitz1/WhereToIbiza.txt
written_2/travel_guides/berlitz1/WhereToIsrael.txt
written_2/travel_guides/berlitz1/WhereToJerusalem.txt
written_2/travel_guides/berlitz1/WhereToLakeDistrict.txt
written_2/travel_guides/berlitz1/WhereToMadeira.txt
``````

In this example, I am finding the word "Vista" in the realtive path ``written_2/travel_guides/berlitz1/*.txt`` and you can see in the result that it only listed the file names rather than the lines that contain the pattern.

``````terminal
grep -l "vista" written_2/travel_guides/berlitz2/*.txt      
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
written_2/travel_guides/berlitz2/Nepal-WhatToDo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
``````

In this example, I am finding the word "Vista" in the realtive path ``written_2/travel_guides/berlitz2/*.txt`` and you can see in the result that it only listed the **file names** rather than the lines that contain the pattern.

#### When is it useful?
The option ``grep -l`` is especially useful when we want to find out the **names of the files** containing specific patterns in comparison to ``grep`` which only prints out the lines that contain the pattern without showing the file name.

### -h option

``-h`` option displays the **matched lines** that contain the pattern without displaying the filename of the content

``````terminal
grep -h pattern <<fileName>>
``````
``````terminal
grep -h "vista" written_2/travel_guides/berlitz2/*.txt
The Temple of Olympian Zeus is dedicated to Zeus, “king” of the Greek gods. It was imperative that his temple should be fitting for his position, and its dimensions — 250 m (814 ft) long and 130 m (426 ft) wide, with columns of over 17 m (61 ft) in height — are truly majestic. The temple took 700 years to complete and it was Hadrian who finished the task in the second century a.d. One hundred and eight columns originally surrounded an inner sanctum that protected a gold-and-ivory statue of Zeus. Today only 15 are still standing, but their Corinthian capitals have a wonderful form and elegance. In ancient times, the temple sat close to the banks of the River Ilissos creating an even more beautiful vista. Today the river still flows, but its path lies beneath the city.
At the eastern end of Paradise Island stands a much older structure that offers the opportunity for restful contemplation. The Cloisters are the remains of a 14th-century monastery that was bought in France by Huntingdon Hartford, taken apart, and rebuilt in the grounds of his home, now the Ocean Club hotel. Hartford set the small courtyard on a rise several hundred yards away from the house and created an elaborate garden to lead to the edifice. The Versailles Gardens, based on Louis XIV’s formal palace gardens outside Paris, have terraces, fountains, and statues that provide a soothing vista, leading the eye from the house to the cloisters. It is possible to visit the Cloisters during daylight hours — they stand next to the only road that traverses the island — but they are used regularly for wedding ceremonies, so you might find them closed.
Farther along the coast road, 8 km (5 miles) past Buenavista del Norte, lies the most westerly point on Tenerife, the Punta de Teno. From here there are panoramic views across to La Gomera and looking south to the massive cliffs of Los Gigantes. Turn back to Buenavista and take a marked turn inland to Masca. Be warned, though, this is absolutely not a drive to be undertaken by inexperienced or nervous drivers. Initially the road, although ascending through the arable mountainside, is no problem; but this soon changes once the entrance to the vertiginous valley is reached. One glance at the narrow, steeply twisting road on either side will be enough to realize why, up to only a ...
``````

In this example, we are trying the option ``-h`` and we can see that it printed out all the **matched lines** with the pattern without printing out the filename.

``````terminal
grep -h "vista" written_2/travel_guides/berlitz2/*.txt
The Temple of Olympian Zeus is dedicated to Zeus, “king” of the Greek gods. It was imperative that his temple should be fitting for his position, and its dimensions — 250 m (814 ft) long and 130 m (426 ft) wide, with columns of over 17 m (61 ft) in height — are truly majestic. The temple took 700 years to complete and it was Hadrian who finished the task in the second century a.d. One hundred and eight columns originally surrounded an inner sanctum that protected a gold-and-ivory statue of Zeus. Today only 15 are still standing, but their Corinthian capitals have a wonderful form and elegance. In ancient times, the temple sat close to the banks of the River Ilissos creating an even more beautiful vista. Today the river still flows, but its path lies beneath the city.
At the eastern end of Paradise Island stands a much older structure that offers the opportunity for restful contemplation. The Cloisters are the remains of a 14th-century monastery that was bought in France by Huntingdon Hartford, taken apart, and rebuilt in the grounds of his home, now the Ocean Club hotel. Hartford set the small courtyard on a rise several hundred yards away from the house and created an elaborate garden to lead to the edifice. The Versailles Gardens, based on Louis XIV’s formal palace gardens outside Paris, have terraces, fountains, and statues that provide a soothing vista, leading the eye from the house to the cloisters. It is possible to visit the Cloisters during daylight hours — they stand next to the only road that traverses the island — but they are used regularly for wedding ceremonies, so you might find them closed.
``````

In this example, we are trying another specified pattern ``Rocha``, and we can see that, as we expected, it prints out the lines that contained the specified pattern

#### When is it useful?
The option ``grep -h`` is especially helpful when we are searching for a parttern or word and only cares about their context, do not need its fileName. For instance, if we want to read more about "vista" but do not need to know which file is the output from, then ``grep -h`` is much helpful than ``grep`` since it does not print out the information that we do not need - the file name

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


``````terminal
grep -w pattern <<fileName>>
``````
<img width="567" alt="截屏2023-02-09 下午2 18 41" src="https://user-images.githubusercontent.com/114774291/217952257-32e475e2-24db-4ce9-8b9d-1780fd92a6c7.png">

In this picture, we both tried the pattern ``Vist`` and ``Vista``. Because there are no whole word that is the exactly same as "Vist" so we're not printing out anything. However, when we are trying pattern ``Vista`` because we know that it contains words exactly the same as "Vista",results are printed out this time.

<img width="568" alt="截屏2023-02-09 下午2 25 05" src="https://user-images.githubusercontent.com/114774291/217953598-e851df69-2479-49ab-b260-279b0bb6b484.png">

We can use the picture above to compare the result of this command without ``-w`` option with the result with ``-w`` option. We can see that because there is no **whole word** limitation, it printed out something rather than nothing. So in this comparison, we can see that the ``-w`` constraints the result to only the whole words that contain the pattern.

<img width="569" alt="截屏2023-02-09 下午2 34 23" src="https://user-images.githubusercontent.com/114774291/217954578-9c9b4876-67b6-435c-a4a7-0be903579703.png">

In this picture we can see that because there are no whole word that is exactly the same as "abou", it prints out nothing, which is consistant with out expectation.

#### Source cited
The most coomand option can be find on <https://www.geeksforgeeks.org/grep-command-in-unixlinux/>

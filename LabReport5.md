# Lab Report 5

For this lab, I will redo the task for LabReport3 and explore options for the ``less`` command

## -N option

**``less -N`` prints out the line number with the content in the given file**

In this example, we can see that it printed out the line number of ``HandRMallorca.txt``

``````terminal
wushengqi@wushengqideMacBook-Pro berlitz1 % less -N HandRMallorca.txt 

      1 
      2   
      3   
      4     
      5       
      6         Recommended Hotels
      7         The Balearics were formally a maze of down-market concrete
      8         block hotels brutally clustered right on top of once-pristine beaches
      9         and coves.Today the trend is toward providing more discerning travelers
     10         with more authentic and upscale accommodations, frequently in old
     11         farmhouses and manor houses, as well as short- and long-term rentals.
     12         Many hotels on both islands are still beholden to the large tour
     13         operators. Only a couple of the establishments recommended below host
     14         tour groups; we make no effort to review the block-booked resort
     15         hotels, most of which are resoundingly similar in service, ameni
     15 ties,
     16         and facilities.
     17         You are advised to book hotels well in advance, particularly
     18         if planning to visit between June and September. Regardless of when you
     19         go, it’s not wise to descend on either island without reservations
     20         intact. Many hotels close for winter (December-March). As a basic guide
     21         to room prices, we have used the following symbols (for a double room
     22         with bath/shower in high season; prices do not include the 7% VAT, or
     23         IVA, tax):
     24         $below 8,000 pta.
     25         $$8,000-15,000 pta.
     26         $$$15,000-22,000 pta.
     27         $$$$above 22,000 pta.
     28         Spain’s country code is 34; the area code for the Balearics
     29         is 971.
     30       
     31     
     32  
     (END)
``````

The following is another example for ``-N command`` for opening a java file.

``````terminal
wushengqi@wushengqideMacBook-Pro starter % less -N MinHeapInterface.java
      1 public interface MinHeapInterface<E extends Comparable<E>> {
      2     void insert(E element);
      3     E getMin();
      4     E remove();
      5     int size();
      6     void clear();
      7 }
MinHeapInterface.java (END)
``````

**Where are when this is useful?**: The ``-N`` option isespecially useful when we are trying to look at the specific lines of the content. For instance, when we are trying to debug or trying to point to something important to someone else, It is more efficient to say "The error is at line 4" than having others looking for the words from the top to the bottom.

## -E option

**The ``less -E`` option will automatically exits the less command without using ``Ctrl+C``**

In this example, we can see that after using ``-E`` the ``(END)`` has disappeared, meaning it has automatically exited.

``````terminal
wushengqi@wushengqideMacBook-Pro berlitz1 % less -E HandRMallorca.txt


  
  
    
      
        Recommended Hotels
        The Balearics were formally a maze of down-market concrete
        block hotels brutally clustered right on top of once-pristine beaches
        and coves.Today the trend is toward providing more discerning travelers
        with more authentic and upscale accommodations, frequently in old
        farmhouses and manor houses, as well as short- and long-term rentals.
        Many hotels on both islands are still beholden to the large tour
        operators. Only a couple of the establishments recommended below host
        tour groups; we make no effort to review the block-booked resort
        hotels, most of which are resoundingly similar in service, amenities,
        and facilities.
        You are advised to book hotels well in advance, particularly
        if planning to visit between June and September. Regardless of when you
        go, it’s not wise to descend on either island without reservations
        intact. Many hotels close for winter (December-March). As a basic guide
        to room prices, we have used the following symbols (for a double room
        with bath/shower in high season; prices do not include the 7% VAT, or
        IVA, tax):
HandRMallorca.txt
``````

The following is another example for ``less -E`` option, in this example we can also see that the ``(END)`` has disappeared and we do not need to press ``Ctrl + C`` to exit.

``````terminal
wushengqi@wushengqideMacBook-Pro berlitz1 % less -E IntroMadeira.txt 


  
  
    
      
        Madeira and the Madeirans
        A mere speck in the middle of the Atlantic Ocean, Madeira
        has all the elements of a mysterious dream world. The volcanic island
        is thickly draped with vegetation, a colorful riot of flowers and fruit
        trees. Rugged mountains peek through the clouds, and microclimates
        hover over isolated villages. Spectacular cliffs crash hundreds of feet
        below to the deep blue surf.
        Even though foreign invaders stormed Portugal around 2000
        b.c. , Madeira was discovered only a few decades before Columbus made
        his way to America. Though part of the Portuguese empire since the
        great expedition teams of the 15th century claimed it for King João I,
        Madeira is nearer to Africa than Lisbon. It lies 600 km (375 miles) off
        the coast of Morocco and nearly 1,000 km (600 miles) southwest of the
        Portuguese capital.
        Formed from volcanic eruptions many millions of years ago,
        Madeira, like the Canary Islands, is an archipelago. The land is like
        an iceberg; massive mountains poke through the clouds, forming the mere
        tip of a submerged mass. Only one other island in the small group is
IntroMadeira.txt
``````

**Where this is useful?**: When we cannot press "Ctrl" ot "C" button or we only want to have a quick glimpse on the content of the given file, we can see the ``-E`` option to save us some time.

## -f option

**This option will force the ``less`` command to open non-file things such as directories.**

For instance, in this example, we are trying to ``less`` a directory. Normally it will not work because `travel_guides` is a directory; However, with ``-f`` we can see that it still opened the directory although there are nothing printed out.

``````terminal
wushengqi@wushengqideMacBook-Pro written_2 % less travel_guides 
travel_guides is a directory
wushengqi@wushengqideMacBook-Pro written_2 % less -f travel_guides 








~
~
~
~
~
~
~
~
~
~
~
~
~
~
~
(END)
``````

In this example, we can see that if we do not use ``-f``, the terminal will ask it you are going to see a binary file. But with ``-f``, it will immediately open the .jar file without asking.

``````terminal
wushengqi@wushengqideMacBook-Pro lib % less junit-4.13.2.jar 
"junit-4.13.2.jar" may be a binary file.  See it anyway? 
wushengqi@wushengqideMacBook-Pro lib % less -f junit-4.13.2.jar 
PK^C^D
^@^@^H^@^@<F2><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@    ^@^@^@META-INF/PK^C^D^T^@^H^H^H
^@<F2><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^T^@^@^@META-INF/MANIFEST.MFu<8F><CF>^N^A1^P<87><EF><9B><EC>;<F4>^EZ<D6><E2><D0>ESCN6VDp<95>f;l<E9><9F>Mw*<BC><BD>"<D6>^AǙof<BE>ߔª^C<B4>Hw<E0>[<E5>,'^Y<EB><A7><C9><DC>4^Z^LX^T^X<9B>^QZ<E9><'<C5><D6>*<FC>
<A2>ESC<85>^Z:8   <E8>L^D^U-<9D>^L^Z<E8>R<98>HO<E1><D7>jg^]<B2>,g<83>?b:<97>݁iP^Z<E9><F4>Ɖ^Q<BE>zՒ^V<F2><FC>H>f<FD><FD>x<94>&3^O^BA><C7>&<8D><A8>j <A5><B8><80>%9<CB>X<F6>eٮ^W<9C>Ԉ^M<EF><F5><9E>^Z<E6><FC>1~<E2><AB>Z]<C0>^?R<AE>4\CK<DE> M<D2>
<E4>^NPK^G^H<9C><B9><C5>̼^@^@^@A^A^@^@PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^F^@^@^@junit/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^M^@^@^@junit/textui/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^P^@^@^@junit/framework/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^M^@^@^@junit/runner/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^Q^@^@^@junit/extensions/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^D^@^@^@org/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@
^@^@^@org/junit/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@^W^@^@^@org/junit/experimental/PK^C
^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@ ^@^@^@org/junit/experimental/theories/PK^C^D
^@^@^H^@^@<EB><8B>MR^@^@^@^@^@^@^@^@^@^@^@^@*^@^@^@org/junit/experimental/theories/suppliers/PK^C^D
junit-4.13.2.jar
``````

**Where and when this is useful?**: The ``-f`` option is especially useful when we are trying to print out a non-regular file such as this binary file or a directory. It will save us from going through the procedure of asking whether we want to look at the file. 

## -s option

**The ``less -s`` option turns multiple ``skip lines`` into only one skip line**

This is an example of using ``-s`` option. We can see in the previous example that there are more than five skip lines for ``HandRMallorca.txt``. After using ``-s``, the skip lines are turned into only one skip line.

``````terminal
wushengqi@wushengqideMacBook-Pro berlitz1 % less -s HandRMallorca.txt 

        with more authentic and upscale accommodations, frequently in old
        farmhouses and manor houses, as well as short- and long-term rentals.
        Many hotels on both islands are still beholden to the large tour
        operators. Only a couple of the establishments recommended below host
        tour groups; we make no effort to review the block-booked resort
        hotels, most of which are resoundingly similar in service, amenities,
        and facilities.
        You are advised to book hotels well in advance, particularly
        if planning to visit between June and September. Regardless of when you
        go, it’s not wise to descend on either island without reservations
        intact. Many hotels close for winter (December-March). As a basic guide
        to room prices, we have used the following symbols (for a double room
        with bath/shower in high season; prices do not include the 7% VAT, or
        IVA, tax):
        $below 8,000 pta.
        $$8,000-15,000 pta.
        $$$15,000-22,000 pta.
        $$$$above 22,000 pta.
        Spain’s country code is 34; the area code for the Balearics
        is 971.
      
    
  
(END)
``````

This is another example using ``-s`` option.

``````terminal
wushengqi@wushengqideMacBook-Pro berlitz1 % less -s IntroIsrael.txt

        the country has begun to realise its considerable potential for
        beach-style tourism. The fast-paced metropolis of Tel Aviv boasts
        beautiful white sands, while other parts of the country have their own
        unique features. It is perfectly feasible to spend a fortnight in
        Eilat, exploring the Red Sea, lying on the beaches, journeying into the
        Negev Desert — and never see a religious building or an archaeological
        site.
        After an exhausting day on the go or at the beach, you can
        rest assured that you’ll be able to relax in comfortable hotels,
        hospices, and restaurants. Israelis are delighted that people from
        everywhere visit their country, and welcome you with genuine warmth.
        Nor are you likely to encounter a language problem, as English is
        taught in all schools and is widely spoken.
        It has been suggested that it’s impossible for any
        foreigner to understand the Israeli psyche. Possibly no other country
        has had such a turbulent history. Visits to Masada and Yad Vashem (the
        Holocaust Museum) may give you an inkling of the capacity for tragedy
        and heroism embodied in both that history and the modern State of
        Israel. Yet, despite all the displacement and suffering, the settlers
        of this land continue to be friendly and welcoming.
      
    
  
(END)
``````

**Where and when this is useful?**: The option ``-s`` is especially useful when there are a lot of skip lines in the file. This option will save us some time from proventing us from scrolling up and down.

#### Source:

<https://phoenixnap.com/kb/less-command-in-linux#:~:text=The%20less%20command%20is%20a,resulting%20in%20fast%20loading%20speeds.>

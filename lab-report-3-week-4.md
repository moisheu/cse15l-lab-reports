# Lab report 4
This lab report will demonstrate different usages for command line command ``grep`` 

## ``grep -w``
When appending -w grep will only return exact matches of strings within a file(s).

Example 1:

**What its doing**: when using ```grep -w "Brian"``` it pulls up only exact matches of "Brian", any variations with mixed case-lock will not return regardless if they contain the same letters.

**Why it is useful**: This can be useful for retrieving specific names, case sensitive words, or even code as it will only return the exact case sensitive instances of a string. Further, in this context it returns the line in which it was found so it retrieves "Brian" as well as the context in which they are mentioned making this a highly useful tool for retrieving information as well as also previewing its context. 

**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:250$ grep -w "Brian" chapter-1.txt
```

**Output**

```bash 
At 8:59, Flight 175 passenger Brian David Sweeney tried to call his wife, Julie. He left a message on their home answering machine that the plane had been hijacked. He then called his mother, Louise Sweeney, told her the flight had been hijacked, and added that the passengers were thinking about storming the cockpit to take control of the plane away from the hijackers.
```

----

Example 2:

**What its doing**: when using ```grep -w "physician"``` it pulls up only exact matches of "physician", any variations with mixed case-lock will not return regardless if they contain the same letters.

**Why it is useful**: This can be useful for retrieving specific names, case sensitive words, or even code as it will only return the exact case sensitive instances of a string. Though this example is less fruitful in terms of context, it still serves its purpose and usefulness by being able to identify the instances of occurance quickly and efficiently. 


**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:251$ grep -w "physician" chapter-2.txt
```

**Output**

```bash 
physician, Ayman al Zawahiri, arranged from their Afghan headquarters for an Arabic
```
---

Example 3:

**What its doing**: when using ```grep -w "embassies"``` it pulls up only exact matches of "embassies", any variations with mixed case-lock will not return regardless if they contain the same letters.

**Why it is useful**: This can be useful for retrieving specific names, case sensitive words, or even code as it will only return the exact case sensitive instances of a string. Like the aforementioned examples, this returns all instances, case sensitive, with their context. Specifically in this example, it is highly useful by returning multiple instances of "embassies" making this a highly effective tool for finding all instances quickly. 

**Input**

```bash
[cs15lfa22gs@ieng6-201]:911report:252$ grep -w "embassies" chapter-3.txt
```

**Output**

```bash 
organized the bombing of two U.S. embassies. In this chapter, we trace the parallel attach�. Increasingly, the embassies themselves were overshadowed by powerful membassies in Nairobi, Kenya, and Dar es Salaam, Tanzania. Suspicion quickly focused capability to coordinate two nearly simultaneous attacks on U.S. embassies in suggesting imminent Bin Ladin attacks on the U.S. embassies in Qatar and Ethiopia.
```
---

## ``cat [file] | grep -wi [text]``
This command prints out instances of a text within a file by first calling ``cat`` which prints the content of a file, then piping the contents to grep -wi which seeks out instances of string regardless of case 

Example 1:

**What its doing**: when using ```cat chapter-1.txt | grep -wi "scream"``` it first prints out the entirety of chapter-1.txt , taking this output and piping it (basically funneling the results over to the grep portion) where grep will retrieve the instances of "scream" while -wi ensures that grep is retrieving all instances of scream regardless of case. 

**Why it is useful**: This can be useful for retrieving all instances of words regardless of case. Particularly in text files, this can be used to account for human error in forgetting cases and retrieve all instances of an argument. 


**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:258$ cat chapter-1.txt | grep -wi "scream"
```
**Output**
```bash 
The call ended abruptly. Lee Hanson had heard a woman scream just before it cut off. He turned on a television, and in her home so did Louise Sweeney. Both then saw the second aircraft hit the World Trade Center.
```
---

Example 2:

**What its doing**: when using ```cat chapter-2.txt | grep -wi "Usama"``` it first prints out the entirety of chapter-2.txt , taking this output and piping it (basically funneling the results over to the grep portion) where grep will retrieve the instances of "Usama" while -wi ensures that grep is retrieving all instances of scream regardless of case. 

**Why it is useful**: This can be useful for retrieving all instances of words regardless of case. Particularly in text files, this can be used to account for human error in forgetting cases and retrieve all instances of an argument. In this example specifically, it demonstrates that -wi does not grab exclusively mixed case or lowercase terms but also cased terms showing the broadness of its usefulness as it does not exclude names, or the start of sentences. 

**Input**
```bash 
[cs15lfa22gs@ieng6-201]:911report:257$ cat chapter-2.txt | grep -wi "Usama"
```
**Output**
```bash 
In February 1998, the 40-year-old Saudi exile Usama Bin Ladin and a fugitive Egyptian
                from the Middle East. Some were Saudis, and among them was Usama Bin Ladin.
                Bin Ladin's close comrades were more peers than subordinates. For example, Usama
```
---

Example 3:

**What its doing**: when using ```cat chapter-3.txt | grep -wi "Embassy"``` it first prints out the entirety of chapter-3.txt , taking this output and piping it (basically funneling the results over to the grep portion) where grep will retrieve the instances of "Embassy" while -wi ensures that grep is retrieving all instances of scream regardless of case. 

**Why it is useful**: This can be useful for retrieving all instances of words regardless of case. Particularly in text files, this can be used to account for human error in forgetting cases and retrieve all instances of an argument. In this example specifically, it demonstrates that -wi does not grab exclusively mixed case or lowercase terms but also cased terms showing the broadness of its usefulness as it does not exclude names, or the start of sentences. This case in particular was very generous about providing context as is grep in general, in combination showing all the ways -wi provides the useability in accounting for textual and grammatical contexts retrieving strings regardless of case. 

**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:256$ cat chapter-3.txt | grep -wi "Embassy"
```
**Output**

```bash 
embassy official was the logical person to represent U.S. interests.
                Americans were held hostage at the U.S. embassy in Tehran, ended the State
                Ladin unit was gearing up, Jamal Ahmed al Fadl walked into a U.S. embassy in Africa,
                different U.S.embassy. More confirmation was supplied later that year by
            After the embassy attacks, the Pentagon offered this plan to the White House.
            The day after the embassy bombings, Tenet brought to a principals meeting
                was for mass killing. Two days before the embassy bombings, Clarke's staff wrote
            The period after the August 1998 embassy bombings was critical in shaping U.S. policy
            Even after the embassy attacks, Bin Ladin had been responsible for the deaths of
                Ladin, and the embassy bombings gave him new scope for pursuing his obsession.
                In the summer before the embassy bombings, the State Department had been heavily
                1998, just two days before the embassy bombings.
            By late 1999, more than a year after the embassy bombings, diplomacy with Pakistan,
            As part of the response to the embassy bombings, President Clinton signed a
                a planned attack on the U.S. embassy in Tirana, and did lead to the rendition of a
                number of al Qaeda-related terrorist operatives. After the embassy bombings, there
                attack on the U.S. embassy in Uganda, and a number of suspects were arrested. On
                just led the United States to mistakenly bomb the Chinese embassy in Belgrade during
```
---

## ``grep -n``
``grep -n`` finds strings while the ``-n`` will also print out line numbers associated with instances matching the argument. However this is case sensitive. 

Example 1:

**What its doing**: when using ```grep -n "pushed" chapter-1.txt``` it takes all instances of "pushed" and also returns the line number 

**Why it is useful**: This is useful for retrieving instance AND location for easy access and identification if any citing or fixing is needed. 

**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:267$ grep -n "pushed" chapter-1.txt
```
**Output**

```bash 
34:    While Atta had been selected by CAPPS in Portland, three members of his hijacking team-Suqami, Wail al Shehri, and Waleed al Shehri-were selected in Boston. Their selection affected only the handling of their checked bags, not their screening at the checkpoint. All five men cleared the checkpoint and made their way to the gate for American 11. Atta, Omari, and Suqami took their seats in business class (seats 8D, 8G, and 10B, respectively). The Shehri brothers had adjacent seats in row 2 (Wail in 2A, Waleed in 2B), in the firstclass cabin. They boarded American 11 between 7:31 and 7:40. The aircraft pushed back from the gate at 7:40.
36:    Shehhi and his team, none of whom had been selected by CAPPS, boarded United 175 between 7:23 and 7:28 (Banihammad in 2A, Shehri in 2B, Shehhi in 6C, Hamza al Ghamdi in 9C, and Ahmed al Ghamdi in 9D). Their aircraft pushed back from the gate just before 8:00.
100:    United 175 pushed back from its gate at 7:58 and departed Logan Airport at 8:14. By 8:33, it had reached its assigned cruising altitude of 31,000 feet. The flight attendants would have begun their cabin service.
126:    American 77 pushed back from its gate at 8:09 and took off at 8:20. At 8:46, the flight reached its assigned cruising altitude of 35,000 feet. Cabin service would have begun. At 8:51, American 77 transmitted its last routine radio communication. The hijacking began between 8:51 and 8:54. As on American 11 and United 175, the hijackers used knives (reported by one passenger) and moved all the passengers (and possibly crew) to the rear of the aircraft (reported by one flight attendant and one passenger). Unlike the earlier flights, the Flight 77 hijackers were reported by a passenger to have box cutters. Finally, a passenger reported that an announcement had been made by the "pilot" that the plane had been hijacked. Neither of the firsthand accounts mentioned any stabbings or the threat or use of either a bomb or Mace, though both witnesses began the flight in the first-class cabin.
```

Example 2:

**What its doing**: when using ```grep -n "God" chapter-2.txt``` it takes all instances of "God" and also returns the line number 

**Why it is useful**: This is useful for retrieving instance AND location for easy access and identification if any citing or fixing is needed. But also useful in identifying proper nouns vs phrases which is shown in this case while providing exact number lines regardless of multiple instances. 

**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:270$ grep -n "God" chapter-2.txt
```
**Output**
```bash 
12:                declared war against God and his messenger, they called for the murder of any
78:            Islam Islam (a word that literally means "surrender to the will of God") arose in
80:                from the one and only God, the God of Abraham and of Jesus. These revelations,
83:                from Abraham through Jesus, complete God's message to humanity. The Hadith, which
110:                legislation, only prove these rulers to be false Muslims usurping God's authority
151:                as a struggle between God and Satan. All Muslims-as he defined them-therefore must
```
Example 3:

**What its doing**: when using ```grep -n "Second" chapter-1.txt``` it takes all instances of "Second" and also returns the line number 

**Why it is useful**: This is useful for retrieving instance AND location for easy access and identification if any citing or fixing is needed. In this example grep is default case sensitive thus will return case specific instances of "Second" used as a transition rather than an adjective which can be useful when trying to identify between the two. 

**Input**
```bash 
[cs15lfa22gs@ieng6-201]:911report:273$ grep -n "Second" chapter-3.txt
```
**Output**
```bash 
36:            Second, the FBI and the Justice Department did excellent work investigating the
132:                management ranks had little counterterrorism experience. Second, priorities were
259:            Second, the new division intended to strengthen the FBI's strategic analysis
518:                domestic hijacking had occurred in a decade. Second, the commercial aviation system
1327:                and effectively to protect Americans from terrorism at home and abroad. Second, we
1452:            Second, Congress tends to follow the overall lead of the president on budget issues
3042:                ASSAULTS 141 hit. Second, the administration, and the CIA in particular, was in the
```

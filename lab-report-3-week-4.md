# Lab report 4
This lab report will demonstrate different usages for command line command ``grep`` 

## ``grep -w``
When appending -w grep will only return exact matches of strings within a file(s).

**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:250$ grep -w "Brian" chapter-1.txt
```

**Output**

```bash 
At 8:59, Flight 175 passenger Brian David Sweeney tried to call his wife, Julie. He left a message on their home answering machine that the plane had been hijacked. He then called his mother, Louise Sweeney, told her the flight had been hijacked, and added that the passengers were thinking about storming the cockpit to take control of the plane away from the hijackers.
```

----

**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:251$ grep -w "physician" chapter-2.txt
```

**Output**

```bash 
physician, Ayman al Zawahiri, arranged from their Afghan headquarters for an Arabic
```
---

**Input**

```bash
[cs15lfa22gs@ieng6-201]:911report:252$ grep -w "embassies" chapter-3.txt
```

**Output**

```bash 
organized the bombing of two U.S. embassies. In this chapter, we trace the parallel attach�. Increasingly, the embassies themselves were overshadowed by powerful membassies in Nairobi, Kenya, and Dar es Salaam, Tanzania. Suspicion quickly focused capability to coordinate two nearly simultaneous attacks on U.S. embassies in suggesting imminent Bin Ladin attacks on the U.S. embassies in Qatar and Ethiopia.
```
---
**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:253$ grep -w "embass" chapter-3.txt
```


**Output**

```bash
n/a no output because there are no exact matches. normal grep will return all instances containing "embass"
```
----

## ``cat [file] | grep -wi [text]``
This command prints out instances of a text within a file by first calling ``cat`` which prints the content of a file, then piping the contents to grep -wi which seeks out instances of string regardless of case 


**Input**

```bash 
[cs15lfa22gs@ieng6-201]:911report:258$ cat chapter-1.txt | grep -wi "scream"
```
**Output**
```bash 
The call ended abruptly. Lee Hanson had heard a woman scream just before it cut off. He turned on a television, and in her home so did Louise Sweeney. Both then saw the second aircraft hit the World Trade Center.
```
---
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

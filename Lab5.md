In this lab report, I'm going to give several command line options for `grep`. `grep` allows user to search for certain patterns within file(s).

***

1. ## `-i`
- Ignore uppercase or lowercase when finding certain patterns 
```
$ grep -i "nowhere" travel_guides/berlitz1/WhereToItaly.txt
        different facets of Italy’s daily life. Nowhere is it easier or more
        the Piazza Navona. Nowhere in Rome is the spectacle of Italian street
        gondola that appears out of nowhere. Staying forever is most likely to
        Probably nowhere is there so much spectacular painting on
        Nowhere does a cathedral more distinctly dominate a major
```
notes: Display the word "nowhere" disregarding its case.
```
$ grep -i "keep" travel_guides/berlitz1/WhereToItaly.txt
        Keep your car for use on the open road. In the overcrowded
        covered corridor for Duke Cosimo to keep out of the rain when crossing
        enamel, still keeps perfect time, activating statues of two green
        no hustlers is all but history. A local attempt to keep alive its
        temples, brought here for safe-keeping.
        were just a shopkeeper’s good luck sign. Notice the oil and wine jars
        preferred to keep at a decorous distance, in this splendid suburban
        stylish international crowd keeps its many small hostelries and two
        Piccola — are protected as a zona monumentale. Shopkeepers are happy to
```
notes: Easier for the user to find the patterns without adjusting uppercase to lowercase, vice versa. It's also useful when the user doesn't know the case of the patterns.
- source: [https://man7.org/linux/man-pages/man1/grep.1.html](http://a.com)

2. ## `-n`
- Return the line number of where the patterns match
```
$ grep -n "nowhere" travel_guides/berlitz1/WhereToItaly.txt
1989:        gondola that appears out of nowhere. Staying forever is most likely to
2217:        Probably nowhere is there so much spectacular painting on
```
notes: Locate "nowhere" in terms of line number.
```
$ grep -n "civilization" travel_guides/berlitz1/WhereToItaly.txt
98:        instincts of Western civilization. Only to the uninitiated do Italian
130:        The center of Italy is the cradle of Latin civilization,
759:        provide fascinating evidence of the brilliant Etruscan civilization for
913:        creation to the rise of civilization through the arts and
1454:        The original territory of the ancient civilization of the
```
notes: This option allows user know where the pattern is specifically. 
- source: ChatGPT

3. ## `-r`
- Search the pattern through directory, instead of file(s)
```
$ grep -r "overcrowded" travel_guides/berlitz1
travel_guides/berlitz1/HistoryHongKong.txt:        of heads. But this new housing was grimly overcrowded, and even a
travel_guides/berlitz1/WhereToItaly.txt:        Keep your car for use on the open road. In the overcrowded
travel_guides/berlitz1/WhereToEdinburgh.txt:        Edinburgh (today’s Old Town) was overcrowded and unsanitary. The city
travel_guides/berlitz1/WhereToFrance.txt:        window or balcony. These days the students attend overcrowded
travel_guides/berlitz1/WhereToFrance.txt:        houses, picturesque Riquewihr is often overcrowded during the tourist
travel_guides/berlitz1/WhereToFrance.txt:        In summer it’s overcrowded, but that’s part of the fun.
travel_guides/berlitz1/WhereToMallorca.txt:        a pebbly beach, but all tend to be overcrowded with daytrippers. The
travel_guides/berlitz1/WhereToMallorca.txt:        here are very small, and overcrowded in high summer.
travel_guides/berlitz1/WhereToJerusalem.txt:        overcrowded Jewish Quarter of the Old City to more modern and healthy$$
```
notes: Display every occurance of the word "overcrowded" in the directory berlitz1 under travel_guides.
```
???
```
notes: Display every occurance of the word "overcrowded" in the directory berlitz1 under travel_guides. It's useful when the user want to search the pattern across all files under a directory. 
- source: [https://man7.org/linux/man-pages/man1/grep.1.html](http://a.com)

4. ## `-c`
- display the number of times the pattern appears in a file.
```
$ grep -c "nowhere" travel_guides/berlitz1/WhereToItaly.txt
2
```
notes: The word "nowhere" (with lowercase 'n') occurs 2 time in the article WhereToItaly. 
```
$ grep -c "civilization" travel_guides/berlitz1/WhereToItaly.txt
5
```
notes: The word "civilization" (with lowercase 'c') occurs 5 time in the article WhereToItaly. This command line option is useful when you want to know how many times a certain pattern occur in the file. 
- source: [https://en.wikibooks.org/wiki/Grep](http://a.com)

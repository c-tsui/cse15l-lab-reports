In this lab report, I'm showing several different ways of using `find` command.

***

1. ## `-name`
- find the file(s) by its name
```
$ find written_2/non-fiction/OUP/Abernathy/*.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
```
notes: Find all the text files under _Abernathy_. It's useful that user can go thorugh all text files at once.
```
$ find written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
```
notes: Directly find the file called _WhereToLosAngeles.txt_.
- source: Lab Tasks section in CSE15L Lab GitHub week 4 ([https://ucsd-cse15l-w23.github.io/week/week4/](http://a.com))

2. ## `-type` 
- find the file(s) by its type
```
$ find ./written_2  -type d
./written_2
./written_2/non-fiction
./written_2/non-fiction/OUP
./written_2/non-fiction/OUP/Berk
./written_2/non-fiction/OUP/Abernathy
./written_2/non-fiction/OUP/Rybczynski
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Fletcher
./written_2/non-fiction/OUP/Castro
./written_2/travel_guides
./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz2
```
notes: Find the file(s) under _written_2_ by its type, i.e, f for file and d for directory. This is useful when user only wants to know the general idea of the file. 
```
$ find written_2/non-fiction/OUP/Berk -type f
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
```
notes: Find the file(s) under _Berk_.
- source: [https://linuxhint.com/use-the-find-command-in-linux-to-search-files/#:~:text=Syntax%20of%20%E2%80%9Cfind%E2%80%9D%20Command%20in%20Linux&text=Three%20attributes%20go%20with%20the,to%20perform%20with%20the%20file](http://a.com)

3. ## `-size`
- find the file(s) by its size
```
$ find ./written_2  -size +1M
```
notes: Find the file(s) by its size. The above command has no outputs since there's no file under _written_2_ that's larger than 1M.
```
$ find ./written_2  -size -1M -type d
./written_2
./written_2/non-fiction
./written_2/non-fiction/OUP
./written_2/non-fiction/OUP/Berk
./written_2/non-fiction/OUP/Abernathy
./written_2/non-fiction/OUP/Rybczynski
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Fletcher
./written_2/non-fiction/OUP/Castro
./written_2/travel_guides
./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz2
```
notes: Find the directory under _written_2_ which size is smaller than 1M.
- source: ChatGPT

4. ## `-ls`
- list the details of file(s)
```
$ find ./written_2 -type d -ls
8148902        0 drwxr-xr-x    4 claire.tsui      staff                 128 Feb  2 09:45 ./Written_2
8148903        0 drwxr-xr-x    3 claire.tsui      staff                  96 Feb  2 09:45 ./Written_2/non-fiction
8148904        0 drwxr-xr-x    8 claire.tsui      staff                 256 Feb  2 09:45 ./Written_2/non-fiction/OUP
8148915        0 drwxr-xr-x    6 claire.tsui      staff                 192 Feb  2 09:45 ./Written_2/non-fiction/OUP/Berk
8148905        0 drwxr-xr-x   11 claire.tsui      staff                 352 Feb  2 09:45 ./Written_2/non-fiction/OUP/Abernathy
8148952        0 drwxr-xr-x    5 claire.tsui      staff                 160 Feb  2 09:45 ./Written_2/non-fiction/OUP/Rybczynski
8148942        0 drwxr-xr-x   11 claire.tsui      staff                 352 Feb  2 09:45 ./Written_2/non-fiction/OUP/Kauffman
8148935        0 drwxr-xr-x    8 claire.tsui      staff                 256 Feb  2 09:45 ./Written_2/non-fiction/OUP/Fletcher
8148920        0 drwxr-xr-x   16 claire.tsui      staff                 512 Feb  2 09:45 ./Written_2/non-fiction/OUP/Castro
8148956        0 drwxr-xr-x    4 claire.tsui      staff                 128 Feb  2 09:45 ./Written_2/travel_guides
8148957        0 drwxr-xr-x  103 claire.tsui      staff                3296 Feb  2 09:45 ./Written_2/travel_guides/berlitz1
8149059        0 drwxr-xr-x   80 claire.tsui      staff                2560 Feb  2 09:45 ./Written_2/travel_guides/berlitz2
```
notes: Find the directories under _written_2_ and list out its details respectively. It's useful if the user want to know the date it's been modified, etc. 
```
$ find ./Written_2/non-fiction/OUP/Fletcher -type f -ls
8148938      104 -rwxr-xr-x    1 claire.tsui      staff               51325 Feb  2 09:41 ./Written_2/non-fiction/OUP/Fletcher/ch2.txt
8148936       96 -rwxr-xr-x    1 claire.tsui      staff               46376 Feb  2 09:41 ./Written_2/non-fiction/OUP/Fletcher/ch1.txt
8148939       96 -rwxr-xr-x    1 claire.tsui      staff               48389 Feb  2 09:41 ./Written_2/non-fiction/OUP/Fletcher/ch5.txt
8148940      136 -rwxr-xr-x    1 claire.tsui      staff               68106 Feb  2 09:41 ./Written_2/non-fiction/OUP/Fletcher/ch6.txt
8148941      112 -rwxr-xr-x    1 claire.tsui      staff               53257 Feb  2 09:41 ./Written_2/non-fiction/OUP/Fletcher/ch9.txt
8148937       72 -rwxr-xr-x    1 claire.tsui      staff               33013 Feb  2 09:41 ./Written_2/non-fiction/OUP/Fletcher/ch10.txt
```
notes: Find the file(s) under _Fletcher_ and list out its details respectively.
- source: ChatGPT

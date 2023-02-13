# Lab Report 3 - Servers and Bugs (2/13/23)

### 1. grep -v
Inverts the match and displays non-matching lines.

#### a) Find directory names
Command:
```
grep -v ".txt" find-results.txt 
```

Output:
```
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```

#### b) Take out `travel-guides`
Command:
```
grep -v "travel_guides" find-results.txt
```

Output:
```
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
estherxiong@Esthers-MacBook-Pro-2 docsearch % grep -v "travel_guides" find-results.txt
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/non-fiction/OUP/Rybczynski/ch3.txt
written_2/non-fiction/OUP/Rybczynski/ch1.txt
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Kauffman/ch3.txt
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch4.txt
written_2/non-fiction/OUP/Kauffman/ch5.txt
written_2/non-fiction/OUP/Kauffman/ch7.txt
written_2/non-fiction/OUP/Kauffman/ch6.txt
written_2/non-fiction/OUP/Kauffman/ch8.txt
written_2/non-fiction/OUP/Kauffman/ch9.txt
written_2/non-fiction/OUP/Kauffman/ch10.txt
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Fletcher/ch2.txt
written_2/non-fiction/OUP/Fletcher/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch5.txt
written_2/non-fiction/OUP/Fletcher/ch6.txt
written_2/non-fiction/OUP/Fletcher/ch9.txt
written_2/non-fiction/OUP/Fletcher/ch10.txt
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Castro/chR.txt
written_2/non-fiction/OUP/Castro/chP.txt
written_2/non-fiction/OUP/Castro/chQ.txt
written_2/non-fiction/OUP/Castro/chB.txt
written_2/non-fiction/OUP/Castro/chC.txt
written_2/non-fiction/OUP/Castro/chA.txt
written_2/non-fiction/OUP/Castro/chV.txt
written_2/non-fiction/OUP/Castro/chW.txt
written_2/non-fiction/OUP/Castro/chM.txt
written_2/non-fiction/OUP/Castro/chZ.txt
written_2/non-fiction/OUP/Castro/chL.txt
written_2/non-fiction/OUP/Castro/chN.txt
written_2/non-fiction/OUP/Castro/chY.txt
written_2/non-fiction/OUP/Castro/chO.txt
```
What's happening is that grep takes all of the lines and displays the files that don't contain the match. This is useful for finding lines that DON'T match your specific input. For example, if we want to only see the directory names, we can just exclude all the files with .txt. This then lets you focus on a specific, controlled amount of data. 

### 2. grep -c
Displays the count of the matched lines

#### a) Find lines with `travel_guides`
Command:
```
grep -c "travel_guides" find-results.txt
```

Output:
```
182
```

#### b) Find lines with `non-fiction`
Command:
```
grep -c "non-fiction" find-results.txt
```

Output:
```
53
```
What's happening is that grep counts all the lines that match with your input and display the number. This is useful because you can get how many lines there are with a quick command, rather than counting all the contents of matched lines.

### 3. grep -i
Displays the matched lines with case-sensitive searching

#### a) Find lines with `japan`
Command:
```
grep -i "japan" find-results.txt
```

Output:
```
written_2/travel_guides/berlitz1/HistoryJapan.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhatToJapan.txt
written_2/travel_guides/berlitz1/IntroJapan.txt
```

#### b) Find lines with `hongkong`
Command:
```
grep -i "hongkong" find-results.txt
```

Output:
```
written_2/travel_guides/berlitz1/HandRHongKong.txt
written_2/travel_guides/berlitz1/HistoryHongKong.txt
written_2/travel_guides/berlitz1/IntroHongKong.txt
written_2/travel_guides/berlitz1/WhatToHongKong.txt
written_2/travel_guides/berlitz1/WhereToHongKong.txt
```
What's happening is that grep displays all the matching lines with a case-insensitive search. This is useful because regardless of your case variation, it can search for all instances of the word. This allows for more flexible searching if you are indifferent to case variation.

### 4. grep -n
Displays the line numbers of the matching lines

#### a) Find line numbers with `China`
Command:
```
grep -n "China" find-results.txt
```

Output:
```
185:written_2/travel_guides/berlitz2/China-WhereToGo.txt
200:written_2/travel_guides/berlitz2/China-History.txt
227:written_2/travel_guides/berlitz2/China-WhatToDo.txt
```

#### b) Find line numbers with `Bahamas`
Command:
```
grep -n "Bahamas" find-results.txt
```

Output:
```
173:written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt
204:written_2/travel_guides/berlitz2/Bahamas-Intro.txt
206:written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
234:written_2/travel_guides/berlitz2/Bahamas-History.txt
```
What's happening is that grep displays all the numbers lines of the matching lines. This can be useful when you want to locate a specific file.

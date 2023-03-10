#### (I decided to research different commands for lab report 3)

# less -p

According to [geeksforgeeks](https://www.geeksforgeeks.org/less-command-linux-examples/), `less -p` starts the reading of the file at the first occurence of 
a pattern, rather than at the beginning of the file.  
  
  
Example:  
(in a directory that contains `written_2/`)  
  
  
Input: `$ less -p 1908 written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: `Since 1845 the lighthouse here has provided protection for ships off the coast; the present light dates from 1908...(continues)`  
This shows the first line that contains `1908` and the reader continues from there. This is useful if you want to find a word in a file, but you also
want to see more context than just a single line. Otherwise, `grep` would be an easier command to use.
  
# less -N

According to [geeksforgeeks](https://www.geeksforgeeks.org/less-command-linux-examples/), `less -N` shows "output along with line numbers"  
  
Examples:  
  
Input: `$ less -N written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: 
```
1  
2  
3  
4  
5 Where to Go  
6 Puerto Rico is an island of contrasts ...
```
The line numbers make it much easier to see where you are in the file when you go farther into it. This is useful for knowing where to look in the file
if you are planning to make changes.
  
Input: `$ less -N -p 1908 written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: `16 Since 1845 the lighthouse here has provided protection for ships off the coast; the present light dates from 1908...`  
This uses the `-p` option from before to find `1908` again. With `-N` I can now see that the first instance of `1908` in the text appears on line 1908, which
can be useful for editing the text. 


# find -size

According to [geeksforgeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/), `find -size` prints all files with the specified size constraints.  
  
Examples:  
  
Input: `$ find written_2/ -size +100k`  
Output:
```
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToIndia.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToJapan.txt
written_2/travel_guides/berlitz1/WhereToMalaysia.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
written_2/travel_guides/berlitz2/China-WhereToGo.txt
written_2/travel_guides/berlitz2/Portugal-WhereToGo.txt
```
This prints all files in the `written_2/` directory that are bigger than 100 kilobytes. This is useful for knowing which files are taking up the most memory
in your computer.
  
Input: `$ find written_2/ -size -1k`
Output: 
```
written_2/
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Castro
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Rybczynski
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```
This prints all the files that are less than 1 kilobyte. I found it interesting that find also includes the directories as things that have less than 
1 kilobyte.

# find -newer

According to [geeksforgeeks](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/), `find -newer` "searches for files modified/created after" the given
file.    
  
Examples:  
  
Input: `$ find written_2/ -newer written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt `  
Output: 
```
written_2/
written_2/searchtest.txt
written_2/travel_guides/berlitz2
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
This finds all the files within the `written_2/` directory that were created after the Puerto Rico file. I think that this can be useful for remembering what
I was doing previously. If I was doing something and created a lot of files in a coding session, I could find all the files I created to know what I was working with.

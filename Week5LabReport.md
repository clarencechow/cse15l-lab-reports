# grep -c

According to https://www.geeksforgeeks.org/grep-command-in-unixlinux/, `grep -c` "prints only a count of the lines that match a pattern," rather than 
the text of all the lines that match the pattern.  
  
  
Examples:  
(in a directory that contains `written_2/`)  
  
  
Input: `$ grep -c "the" written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: `116`  
This tells you that 116 lines in `PuertoRico-WhereToGo.txt` contain "the". This is useful because if I want to know the number of lines with "the" without
the `-c` option, I would have to count each of the 116 lines manually, or use a separate command to find out how many lines were printed.
  
Input: `$ xargs grep -c "the" < grep-results.txt` (uses the `grep-results.txt` file from week 4)  
Output:
```written_2/travel_guides/berlitz1/HandRHawaii.txt:64
written_2/travel_guides/berlitz1/HandRHongKong.txt:6
written_2/travel_guides/berlitz1/HandRIbiza.txt:4
written_2/travel_guides/berlitz1/HandRIsrael.txt:113
.
.
.
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:61
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:111
```
This tells you the number of lines that contain "the" for each of the text files in the `written_2` directory. This is useful because I am able to see
the number of "the"s in each text file separately, with the way the command lists the text files out.  

# grep -i

According to https://www.geeksforgeeks.org/grep-command-in-unixlinux/, `grep -i` "Ignores, case for matching."  
  
Examples:  
  
Input: `$ grep -c -i "the" written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: `118`  
This example is the same input as the first example, except with `-i` added after `-c`. It differs from the output in the first example because there are two cases of "The" instead of "the".
This is useful because it's very common that when searching
for a word it doesn't matter whether it's capitalized or not.  
  
Input: `$ grep -i -c "puerto rico" written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: `27`  
The file `PuertoRico-WhereToGo.txt` contains zero instances of "puerto rico". It only contains "Puerto Rico," because
the article uses correct capitalization. Using `-i` allows me to make a capitalization error in my search and still find the
number of "Puerto Rico"s because the `grep` command becomes case insensitive.

# grep -n

According to https://www.geeksforgeeks.org/grep-command-in-unixlinux/, `grep -n` displays "the matched lines and their line numbers."  
  
Examples:  
  
Input: `$ grep -n "Parque de las Cavernas" written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: (not the full output because it was a lot of words)
```
108:The Observatory sits in the heart ... Parque de las Cavernas del Río Camuy ... through the rock.
```
This prints the line containing the phrase "Parque de las Cavernas," as `grep` normally would, but also includes the line number(108) at the beginning.
This is useful for finding the line within the file, if I want to make changes to it or for anything else.  
  
Input: `$ grep -n -o "Puerto Rico" written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`
Output: 
```
6:Puerto Rico
10:Puerto Rico
11:Puerto Rico
.
.
.
108:Puerto Rico
111:Puerto Rico
```
This prints only the line numbers and the phrase "Puerto Rico" for the lines that contain it in the text file. This is useful because with a lot of lines
to go through it can be much easier to be shown only line numbers and a short phrase afterwords, rather than the entire line of text.  

# grep -w

According to https://www.geeksforgeeks.org/grep-command-in-unixlinux/, `grep -w` matches the whole word.    
  
Examples:  
  
Input: `$ grep -c -i -w "the" written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt`  
Output: `118`  
This example is the same input as a previous example, except with the `-w` option. The output of 118 matches the previous output, which tells me that all of the instances of "the" are cases of the word "the," and not parts of other words such as "they" or "there."  
  
Input: `$ xargs grep -c -w "the" < grep-results.txt`  
Output:
```
written_2/travel_guides/berlitz1/HandRHawaii.txt:62
written_2/travel_guides/berlitz1/HandRHongKong.txt:5
written_2/travel_guides/berlitz1/HandRIbiza.txt:4
written_2/travel_guides/berlitz1/HandRIsrael.txt:99
.
.
.
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt:60
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt:108
```
This example is also the same input as a previous example but with `-w`. This shows different numbers because it only counts the word "the" and not any words
containing "the" that aren't "the". This is useful for seeing information on an entire directory of text files instead of just one.

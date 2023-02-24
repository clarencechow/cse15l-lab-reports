# 4.
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/Step%204.png?raw=true)  
Keys Pressed: `ssh cs15lwi23ave@ieng6.ucsd.edu<Enter>`  
  
This command logged me into the server because I no longer have to type my password. I typed this entire command manually.  

# 5.
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/Step%205.png?raw=true)  
Keys Pressed: `<Ctrl-c>`, `git clone <Ctrl-v><Enter>`  
  
I used `Ctrl-c` to copy the SSH link(`git@github.com:clarencechow/lab7.git`) to clone. I manually typed `git clone `, then pasted the link I copied with `Ctrl-v`.`<Enter>` finished the command.
This successfully cloned the fork into the server.

# 6.
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/Step%206.png?raw=true)  
Keys Pressed: `cd lab7`, `<Ctrl-c><Ctrl-v><Enter>`, `<Ctrl-c><Ctrl-v> L<Tab>Tests<Enter>`  
  
`cd lab7` changed my directory into `lab7/`. `Ctrl-c` copied `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` from the end of the Week
7 page. `Ctrl-v` pasted this into my command line, then enter ran the command. This command compiled the `ListExamples.java` file and the `ListExamplesTests.java` file.
The next `Ctrl-c` copied `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore` from the end of the Week 7 page and `Ctrl-v` pasted it
into my command line. I then manually typed ` L` and then pressed `<Tab>`, which autocompleted the `L` into `ListExamples`. Afterwards, I manually typed `Tests`
and pressed `<Enter>` to run the command. The output showed that one of the tests failed.

# 7.
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/Step%207.png?raw=true)  
Keys Pressed: `nano L<Tab>.java<Enter>`, `<Ctrl-w>+=<Enter><Ctrl-w><Enter><Ctrl-w><Enter><Ctrl-w><Enter><Left><Backspace>2`, `<Ctrl-o><Enter><Ctrl-x>`  

I manually typed `nano L`, then pressing `<Tab>` autocompleted `L` into `ListExamples`, same as #6. I manually typed `.java`, then pressing `<Enter>` ran the command.
This opened the nano text editor for the file `ListExamples.java` as shown in the image. Next, I pressed `Ctrl-w` to open up the search option in nano, searched `+=`,
then pressed `<Enter>` to find the first instance of `+=` in the file. The element of the file I want to change is close to the fourth instance of `+=`, so I
press `Ctrl-w` then `<Enter>` three more times to get to where I want to be. This works because the search option in nano saves the last thing you searched, so
I only had to press `<Enter>` to search for the next `+=`. After this, my cursor was on the `+` in `+=`. I pressed `<Left>` in order to move to the position my cursor
is in in the image above. Then, `<Backspace>` deleted the `1` in `index1`, and typing `2` changed the variable to `index2`. This fixed the mistake that was in the code
causing it to run an infinite loop. `<Ctrl-o><Enter>` saved the change I made, and `<Ctrl-x>` allowed me to exit the text editor.

# 8.
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/Step%208.png?raw=true)  
Keys Pressed: `<Up><Up><Up><Enter>`, `<Up><Up><Up><Enter>`  
  
Pressing `<Up><Up><Up>` brought me to the command `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` from #6 because it was third in my history,
and pressing `<Enter>` ran the command. 
Doing this again brought me to the command `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests`
because the previous command pushed other commands in the history up one place, so now this command was third in the history.
Pressing `<Enter>` ran the command and produced the output in the image.

# 9.
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/Step%209.png?raw=true)  
Keys Pressed: `git add L<Tab>.java<Enter>`, `git commit -m done<Enter>`, `git push<Enter>`  
  
I manually typed `git add L`, then pressing `<Tab>` autocompleted `L` into `ListExamples`. I manually typed `.java`, then pressing `<Enter>` ran the command. This
added the change I made to `ListExamples.java` so it was ready to be committed. I manually typed out `git commit -m done` and pressed `<Enter>` to run it. This
committed the change I made with the message "done". Then, I typed `git push` and pressed `<Enter>` to run it. This pushed the change I made onto my online
repository.

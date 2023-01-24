# Installing VS Code

Visit the Visual Studio Code website and install the application onto your computer, following the steps on the site and the installer.
When VS Code is finished installing, open it from your files. VS Code should show this screen: ![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/connecting_screenshot.png?raw=true)

# Remotely Connecting

Install git on your computer by downloading the installer from the git website. Make sure to keep git installing in Program Files, which is the default location. When I moved it to a different location VS Code was unable to find it. After downloading git, follow [these steps](https://stackoverflow.com/a/50527994) to set the default terminal on VS Code to git bash. On the git bash terminal, run the command "ssh [account name]@ieng6.ucsd.edu". Type "yes" to continue connecting and then type your password when prompted. Afterwards, the terminal should display this: ![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/connecting_screenshot.png?raw=true)

# Trying Some Commands

After connecting to the remote server, you can try using some git commands, such as cd or cat. Some commands I tried are:  
`cd` - command to change my directory  
`pwd` - prints the current working directory
![Image](https://github.com/clarencechow/cse15l-lab-reports/blob/main/commands_screenshot.png?raw=true)  
Some other commands to try are:  
`ls` - prints the files in the current directory, excluding hidden files  
`ls -a` - prints the files in the current diretory, including hidden files  
`cat /home/linux/ieng6/cs15lwi23/public/hello.txt` - prints the contents of the hello.txt file that should be in the your current directory

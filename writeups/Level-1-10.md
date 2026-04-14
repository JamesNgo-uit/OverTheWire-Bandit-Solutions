## level 0 -> level 1

**Goals:** Access the server and find the password stored in a file called "readme" located in the home directory.

**Commands Used:**
* `ssh`: To connect to the server using the Secure Shell(SSH).
* `ls`: To list files in the current directory.
* `cat`: To read the content of the file.

**My logic:** First, I establised an SSH connection to the bandit server. Once logged in, I used `ls` command to confirm the existence of the "readme" file. Finally, I used `cat` command to display the password on the screen.

**Key concept:** Basic Linux Navigation and file reading.

---

## level 1 -> level 2

**Goals:** The password for the level 2 which is stored in a file called " - ".

**Commands Used:**
* `cat`: To read the content of the file.

**My logic:** I realized that we cannot `cat` the " - " file in regular way. Because, it's related to the flags which are the options to modify the behavior of the command. To read the file named " - " we need to use `./` relative path to tell the command exactly where the file is located.

**Key concept:** Basic Linux Navigation and file reading 

## level 0 -> level 1

**Goals:** Access the server and find the password stored in a file called "readme" located in the home directory.

**Commands Used:**
* `ssh`: To connect to the server using the Secure Shell(SSH).
* `ls`: To list files in the current directory.
* `cat`: To read the content of the file.

**My logic:** First, I establised an SSH connection to the bandit server. Once logged in, I used `ls` command to confirm the existence of the "readme" file. Finally, I used `cat` command to dislay the password on the screen.

**Key concept:** Basic Linux Navigation and file reading.


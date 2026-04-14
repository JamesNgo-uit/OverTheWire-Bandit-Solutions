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

**My logic:** I realized that simply running `cat -` does not work because the dash ( - ) is typically interpreted by Linux commands as a flag or an indicator for Standard Input (stdin). To bypass this and treat the dash as a literal filename, I used the relative path `./-`. This explicitly tells the `cat` command exactly where the file is located within the current directory.

**Key concept:** Basic Linux Navigation and file reading 

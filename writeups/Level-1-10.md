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

**Goals:** The password for the level 2, which is stored in a file called " - ".

**Commands Used:**
* `cat`: To read the content of the file.

**My logic:** I realized that simply running `cat -` does not work because the dash ( - ) is typically interpreted by Linux commands as a flag or an indicator for Standard Input (stdin). To bypass this and treat the dash as a literal filename, I used the relative path `./-`. This explicitly tells the `cat` command exactly where the file is located within the current directory.

**Key concept:** Basic Linux Navigation and file reading 

---

## level 2 -> level 3

**Goals:** The password for the next level is stored in a file called "--spaces in this filename--" located in the home directory.

**Commands Used:**
* `cat`: To read the content of the file.
**Example:** `cat ./--spaces\ in\ this\ filename--`.

**My logic:** I discovered that the shell treats spaces as delimiters (separators) between commands and arguments. If I try to `cat ./--spaces in this filename--`. The shell thinks I am trying to read four separate files.\ 
To bypass this, I used backslash escaping (e.g.,` spaces\ in\ this\ filename`) to tell the shell to treat spaces as literal characters rather than separators.\
Other than this approach, I discovered two better ways that are used in professional methods:
1. **Quoting:** Enclosing the filename in double quotes (cat "./--spaces in this filename--").
2. **Tab Completion:** In the real-world scenario, pressing the `TAB` key allows the shell to automatically escape the spaces for you, which is faster and prevents typos.
 
**Key concept:** Basic Linux Navigation and file reading


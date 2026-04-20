## level 0 -> level 1

**Goals:** Access the server and find the password stored in a file called "readme" located in the home directory.

**Commands Used:**
* `ssh`: To connect to the server using the Secure Shell(SSH).
* `ls`: To list files in the current directory.
* `cat`: To read the content of the file.

**My logic:** First, I established an SSH connection to the bandit server. Once logged in, I used `ls` command to confirm the existence of the "readme" file. Finally, I used `cat` command to display the password on the screen.

**Key concept:** Basic Linux Navigation and file reading.

---

## level 1 -> level 2

**Goals:** The password for the level 2, which is stored in a file called " - ".

**Commands Used:**
* `cat`: To read the content of the file.

**My logic:** I realized that simply running `cat -` does not work because the dash ( - ) is typically interpreted by Linux commands as a flag or an indicator for Standard Input (stdin). To bypass this and treat the dash as a literal filename, I used the relative path `./-`. This explicitly tells the `cat` command exactly where the file is located within the current directory.

**Key concept:** Basic Linux Navigation and file reading.

---

## level 2 -> level 3

**Goals:** The password for the next level is stored in a file called "--spaces in this filename--" located in the home directory.

**Commands Used:**
  `cat ./--spaces\ in\ this\ filename--`\
* `cat`: To read the content of the file. 

**My logic:** I discovered that the shell treats spaces as delimiters (separators) between commands and arguments. If I try to `cat ./--spaces in this filename--`. The shell thinks I am trying to read four separate files.\ 
To bypass this, I used backslash escaping (e.g.,` spaces\ in\ this\ filename`) to tell the shell to treat spaces as literal characters rather than separators.\
Other than this approach, I discovered two better ways that are used in professional methods:
1. **Quoting:** Enclosing the filename in double quotes (cat "./--spaces in this filename--").
2. **Tab Completion:** In the real-world scenario, pressing the `TAB` key allows the shell to automatically escape the spaces for you, which is faster and prevents typos.
 
**Key concept:** Basic Linux Navigation and file reading.

---

## level 3 -> level 4

**Goal:** The password for the next level is stored in a hidden file, which is located in the "inhere" directory.

**Commands Used:**
  `ls -a`\
* `ls`: To list files in the current directory.
* `cat`: To read the content of the file.

**My logic:** I observed that hidden files are not displayed by the standard `ls` command. In Linux, files starting with a dot-often called dotfiles- are hidden by default to keep directory listing clean. To reveal the password file, I appended the `-a`(all) to the `ls` command. This instructs the shell to list all the entries, including those starting with a dot, allowing me to identify the hidden directory. 

**Key concept:** Basic Linux Navigation and file reading.

---

## level 4 -> level 5

**Goal:** The password for the next level is stored in the only human-readable file in the "inhere" directory.

**Commands Used:**
  `file ./*` 
* `file`: The utility used to determine the file type of a specific file.

**My logic:** In this level, the objective was to identify the file type of multiple files within a directory to find human-readable text. I utilized the `file` command. Instead of manually inspecting each file one by one, I used an asterisk wildcard `*` as an argument. This allowed the command to process every file in the current directory simultaneously, quickly revealing which file contained the ASCII text password.

**Key concept:** Data Identification and Efficiency.

---

## level 5 -> level 6

**Goal:** The password for the next level is stored in the "inhere" directory and has all of the following properties: Human-readable, 1033 bytes, and not executable.
 
**Commands Used:** 
  `find . -type f -size 1033c ! -executable`
* `find`: To search for files or directories based on various filters like name, size, type, and modification time.

**My logic:** The objective of this level was to locate a specific file based on multiple attributes within a complex directory structure. I utilized the `find` command, using a dot `.` to target the current directory with a recursive search. To narrow down the result, I applied three specific filters:\
1. `-type f`: To restrict the search to regular files only.
2. `-size 1033c`: To target the exact file size of 1033 bytes(where 'c' denotes bytes).
3. `! -executable`: Using the negation operator(`!`) to filter out any files with execution permissions.
By combining these criteria, I was able to isolate the single file that met all security requirements.
 
**Key concept:** Data Identification.

---

## level 6 -> level 7

**Goal:**

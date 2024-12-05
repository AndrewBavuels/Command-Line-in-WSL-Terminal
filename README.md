# Command Line in WSL Terminal

## (In working progress..)

### Table of Contents

1. [What is the terminal?](#1-what-is-the-terminal)
2. [Getting to know the file system through the terminal](#2-getting-to-know-the-file-system-through-the-terminal)
3. [Manipulating files and folders](#3-manipulating-files-and-folders)
4. [Exploring the content of our files](#4-exploring-the-content-of-our-files)
5. [Wildcards](#5-Wildcards)
6. [Shell Redirections](#6-Shell-Redirections)
7. [Pipe Operator Redirections](#7-Pipe-Operator-Redirections)
8. [Chaining Commands with Shell Control Operators](#8-Chaining-Commands-with-Shell-Control-Operators)

---

## 1. What is the terminal?

The terminal is an indispensable tool that anyone in technology must know 👀. It is important because:
  1. **It gives you flexibility 📏.** With just a few commands, you can do a lot.
  2. **It is much faster than a graphical interface 💻.**
  3. **It is your only option if there is no interface 😆,** such as for configuring a remote server.
  4. **You can invoke daemons 👿.** You need to be careful with commands, such as **remove.**

The terminal is a fundamental tool that provides a command line environment through a graphical interface. Here’s a breakdown:

  1. **Terminal:** The black window where you see the command prompt.
  2. **Shell (command line):** The program that executes your commands. In WSL Ubuntu, the default shell is Bash 🍎.
  3. **Command:** A program that you can run from the terminal.

**Pro Tip:** Mastering Linux is a must 🚀.


![outFile](https://github.com/user-attachments/assets/bdb5f8a1-35fe-40d4-bb0f-9c9e562ede01)


## 2. Getting to know the file system through the terminal

Below, I am listing the contents of the **root directory,** showing various system directories and files, with one of the command series that I am going to show you as follows:

- `ls:` Lists the contents of a directory.

```sh
andrewbavuels@the-Legionnaire:/$ ls
Docker  dev   init   lib64       media             mnt   proyectoPersonal  sbin  tmp  wslcdeaCh  wsloOFoIg
bin     etc   lib    libx32      miniconda.html    opt   root              srv   usr  wsleaooND
boot    home  lib32  lost+found  miniconda.html.1  proc  run               sys   var  wsllHHkkc
```
The folder **'/'** after my username (andrewbavuels@the-Legionnaire:), is called the **root directory.** It is the top-most directory in a Unix or Linux file system hierarchy and contains all other files and directories on the system.

- `cd:` Changes the current directory.

```sh
andrewbavuels@the-Legionnaire:~/python$ cd pentaho/
andrewbavuels@the-Legionnaire:~/python/pentaho$
```

- `ls -l:` Lists the contents of a directory in long format, showing detailed information about each file and directory, such as permissions, owner, size, and modification date.

- `ls -h:` Lists the contents of a directory with file sizes in human-readable format, such as KB, MB, or GB.

```sh
andrewbavuels@the-Legionnaire:~/python/pentaho$ ls -h
hs_codes.csv
hs_codes_67d0ca02-86f0-4829-8568-389ab67a38e5.csv:Zone.Identifier
pentaho-etl
template_etl.ipynb
template_etl_oec_9d24a368-c162-49d7-a1e7-d05a278cd880.ipynb:Zone.Identifier
```

- `clear (or crtl+l):` Clears the terminal screen, removing all previous commands and outputs from view.

```sh
andrewbavuels@the-Legionnaire:/$ clear
```

- `cd .. :` Changes the current directory to the parent directory.

```sh
andrewbavuels@the-Legionnaire:~/python/pentaho$ cd ..
andrewbavuels@the-Legionnaire:~/python$
```

- `cd ~ :` Changes the current directory to your home directory.

```sh
andrewbavuels@the-Legionnaire:~$ cd ~
andrewbavuels@the-Legionnaire:~$
```

- `pwd:` Prints the current working directory.

```sh
andrewbavuels@the-Legionnaire:~$ pwd
/home/andrewbavuels
```

- `cd . :` # Refers to the current directory, although if you are as:

- `cd ./['furtherfolder']:` This command changes the current directory to a subdirectory within the relative path

```sh
andrewbavuels@the-Legionnaire:~$ cd ./command_line
andrewbavuels@the-Legionnaire:~/command_line$
```

- `ls -la:` Lists all contents of a directory in long format, including hidden files (files starting with a dot .).

```sh
andrewbavuels@the-Legionnaire:~/command_line$ ls -la
total 1784
drwxr-xr-x  2 andrewbavuels andrewbavuels    4096 Jul 17 09:06  .
drwxr-xr-x 23 andrewbavuels andrewbavuels    4096 Jul 17 07:45  ..
-rw-r--r--  1 andrewbavuels andrewbavuels   17331 Jul 17 09:06  Content.docx
-rw-r--r--  1 andrewbavuels andrewbavuels    3512 Jul 17 09:07  README.md
-rw-r--r--  1 andrewbavuels andrewbavuels  119471 Jul 17 07:50  command-line-cheat-sheet.pdf
-rw-r--r--  1 andrewbavuels andrewbavuels       0 Jul 17 07:50  command-line-cheat-sheet.pdf:Zone.Identifier
-rw-r--r--  1 andrewbavuels andrewbavuels 1664983 Jul 17 07:50  slides.pdf
-rw-r--r--  1 andrewbavuels andrewbavuels     162 Jul 17 09:06 '~$ontent.docx'
```

One of the most important commands for me, especially when uploading my projects to GitHub in a README.md file, is outlining the project structure.

- `tree:` it's a useful tool for visualizing directory structures.

```sh 
andrewbavuels@the-Legionnaire:~$ tree eda
eda
├── data
│   ├── pre_processed
│   │   └── pre_processed_gas_df.csv
│   └── raw
│       ├── measurements.csv
│       └── measurements.csv:Zone.Identifier
├── images
│   ├── question_1.png
│   ├── question_2.png
│   ├── question_3.1.png
│   ├── question_3.2.png
│   ├── question_3.3.png
│   └── question_4.png
├── notebooks
│   └── main.ipynb
└── readme.md

5 directories, 11 files
```
**You will see an example from:** [_Exploratory Data Analysis (EDA) Visualization with Python_](https://github.com/AndrewBavuels/Car-Fuel-Consumption-Part-I-Analysis-before-Predictions)

## 3. Manipulating files and folders

I want to take advantage of this point to create an exclusive folder for the readme...

- `mkdir:` Creates a new directory.

```sh
andrewbavuels@the-Legionnaire:~/command_line$ mkdir README
andrewbavuels@the-Legionnaire:~/command_line$
```

**Suggestion:** For easy manipulation, avoid spaces when naming the file/folder. E.G. Instead of "READ ME", name it like README (no spaces).

- `touch:` Creates an empty file or updates the timestamp of an existing file.

```sh
andrewbavuels@the-Legionnaire:~/command_line$ touch example.txt
andrewbavuels@the-Legionnaire:~/command_line$ ls
 Content.docx               README.md                                      example.txt
```

- `cp file1 file2:` Copies files or directories to file2 or directory2

```sh
andrewbavuels@the-Legionnaire:~/command_line$ cp example.txt example_2.txt
```

- `mv:` Moves or renames files or directories.

```sh
# Renaming a file

andrewbavuels@the-Legionnaire:~/command_line$ mv example.txt example_1
andrewbavuels@the-Legionnaire:~/command_line$ ls
 Content.docx               README.md                                      example_1

 # Moving file to a folder

andrewbavuels@the-Legionnaire:~/command_line$ mv README.md README
andrewbavuels@the-Legionnaire:~/command_line$ cd README/
andrewbavuels@the-Legionnaire:~/command_line/README$ ls
README.md
```

- `rm:` WARNING!!!! Removes files or directories (even Hard Drives)

```sh
andrewbavuels@the-Legionnaire:~/command_line$ rm README.md example_1 example_2.txt 'Recording 2024-07-17 122242.mp4'
```

- `rm -i:` Prevent accidental deletion of important files with a confirmation prompt.

```sh
andrewbavuels@the-Legionnaire:~/command_line$ rm -i LICENSE
rm: remove regular file 'LICENSE'?
```

_At this point, I noticed I made a mistake updating my Github repo and it went like this:_


![Troubleshoot](https://github.com/user-attachments/assets/7497e1ea-231b-46ee-9bdd-757c74832013)

- Moving README.md file to previous folder with **mv README.md ..**

```sh
andrewbavuels@the-Legionnaire:~/command_line/README$ ls
README.md
andrewbavuels@the-Legionnaire:~/command_line/README$ mv README.md ..
andrewbavuels@the-Legionnaire:~/command_line/README$ cd ..
```

- Renaming README folder as Images with **mv README Images**

```sh
andrewbavuels@the-Legionnaire:~/command_line$ mv README Images
```

## 4. Exploring the content of our files

- `head -n:` Displays the first n lines of a file.

```sh
andrewbavuels@the-Legionnaire:~/command_line$ head README.md -n 6
# Command Line in WSL Terminal

### Table of Contents

1. [What is the terminal?](#1-what-is-the-terminal)
2. [Getting to know the file system through the terminal](#2-getting-to-know-the-file-system-through-the-terminal)
```
- `tail -n:` Displays the last n lines of a file.

- `less:` Useful for viewing large files without loading the entire file into memory
**Note:** Once inside less, press '/' to  find some word that will ake you directly to that part of the file.

- `xdg-open:` Opens files and URLs without specify the exact application.

```sh
andrewbavuels@the-Legionnaire:~/command_line$ xdg-open Images
```
## 5. Wildcards

Wildcards are special characters that allow you to find patterns or perform more advanced searches. They apply to files and directories. Wildcards are useful for file or directory segmentation, and they can be used with any command that manipulates files, such as `mv`, `cp`, and `rm`.

### Types of Wildcards

#### Search Everything (*)

The asterisk helps you search for all information within a folder, but you can limit its use. For example, if you want to find files with a ".png" extension, you would write:

- `ls *.<ext> :` Lists files with a specific extension.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$ ls *.mp3
 01-the_magic_numbers-this_is_a_song179.mp3   'Queen of the stoneage - No One Knows.mp3'
'03 stand tall.mp3'                           'Queens Of The Stone Age - No One Knows.mp3'
```

- `ls <word>* :` Lists files and directories that start with a specific word.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$ ls Queen*
'Queen of the stoneage - No One Knows.mp3'    'Queens of the Stone Age - Go With The Flow.mp3'
'Queens Of The Stone Age - No One Knows.mp3'  'Queens of the Stone Age - Monsters In The Parasol.mp3'

Queen:
'Bohemian Rhapsody.mp3'   Desktop.ini  'Queen - Bicycle Race.mp3'   Thumbs.db
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$
```
#### Search by Number of Characters (?)

- `ls <word>? :` Lists files and directories where the <word> is followed by a single character.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$ ls album*
album1  album666
```
- `ls <word>??? :` Lists files and directories where the <word> is followed by exactly three characters.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$ ls album?
album1

andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$ ls album???
album666
```

### Search by Digits

- `ls <word>[<digit>-<digit>]* :` Lists files and directories where the <word> is followed by digits in a specified range.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$ ls album[1-3]*
album1  album2  album3
```
- `ls <word>[<digit>] :` Lists files and directories where the <word> is followed by a single digit.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Music/Rock$ ls album[1-9]*
album1  album2  album3  album4  album5  album6  album7  album8  album9
```

### Search by Character Ranges ([])


- `ls -d [[:upper:]]* :` Lists directories that start with an uppercase letter.


```sh
andrewbavuels@the-Legionnaire:~$ ls -d [[:upper:]]*
Anaconda3-2024.06-1-Linux-x86_64.sh  Anaconda3-2024.06-1-Linux-x86_64.sh:Zone.Identifier
```

- `ls -d [[:lower:]]* :` Lists directories that start with a lowercase letter.

```sh
andrewbavuels@the-Legionnaire:~$ ls -d [[:lower:]]*
amdgpu-install_5.5.50503-1_all.deb  command_line  go1.22.4.linux-amd64.tar.gz  python
anaconda.sh                         databases     listado.txt                  react-app
anaconda3                           eda           misarchivos.txt              web_project
anaconda_deletion                   git_github    mitexto.txt                  wget-log
```

- `ls [cRC]* :` Lists files and directories that start with any of the characters c, R, or C.

```sh
andrewbavuels@the-Legionnaire:~/command_line$ ls [cRC]*
Content.docx  README.md  command-line-cheat-sheet.pdf  command-line-cheat-sheet.pdf:Zone.Identifier
```
### Wildcard Table

| Wildcard              | Function                            |
| --------------------- | ----------------------------------- |
| `*`                   | Search Everything                   |
| `?`                   | Search by Number of Characters      |
| `[]`                  | Search by Specific Characters       |
| `[<digit>-<digit>]`   | Search by Digits                    |

## 6. Shell Redirections

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures/0. CyberpunkNomad (Viajes Inter)$ ls -lh
total 0
drwxrwxrwx 1 andrewbavuels andrewbavuels 4.0K Sep 11  2023 FRANCE
drwxrwxrwx 1 andrewbavuels andrewbavuels 4.0K Nov  8  2023 GERMANY
drwxrwxrwx 1 andrewbavuels andrewbavuels 4.0K Sep 15  2023 ITALY
drwxrwxrwx 1 andrewbavuels andrewbavuels 4.0K Nov  8  2023 SPAIN
drwxrwxrwx 1 andrewbavuels andrewbavuels 4.0K Mar 22 13:25 USA
```
- `ls USA > my_pics.txt`

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures/0. CyberpunkNomad (Viajes Inter)$ ls USA > my_pics.txt
```

- `less my_pics.txt`

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures/0. CyberpunkNomad (Viajes Inter)$ less my_pics.txt

Boston
California
Florida
New York
Washington
```

- **`ls Downloads >> my_files.txt:`** This command uses shell redirection to append the output of a command to a file. Here’s a breakdown:

  - **`ls Downloads:`** This part of the command lists the contents of the `Downloads` directory.

  - **`>>:`** This is the redirection operator used to append the output to a file. If the file specified does not exist, it will be created. If it does exist, the new output will be added to the end of the file without overwriting its existing content.

  - **`my_files.txt:`** This is the file where the output of the `ls Downloads` command will be appended.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre$ ls Pictures > my_files.txt
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre$ less my_files.txt

# Appending files in my_files.txt

andrewbavuels@the-Legionnaire:/mnt/c/Users/andre$ ls Downloads >> my_files.txt
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre$ less my_files.txt
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre$

# Output

0. CyberpunkNomad (Viajes Inter)
1. BARRANQUILLA
2. BOGOTA
3. VIVE COLOMBIA (viajesillos)
4. SPECIAL GUESTS
AuxVID
Camera Roll
Screenshots
desktop.ini
misarchivos.txt
01 escalares vectores matrices tensores.ipynb
Diseño sin título.zip
Docker Desktop Installer.exe
VSCodeUserSetup-x64-1.91.1.exe
dataspell-2024.1.3.exe
desktop.ini
dxwebsetup (1).exe
dxwebsetup (2).exe
dxwebsetup.exe
github-vector-logo-seeklogo.zip
heart.csv
master-web-server.zip
mongosh-2.2.12-win32-x64.zip
my_files.txt (END)
```
### Explanation of Shell Commands and Output

- Attempts to list `76wq3orfih`. The file or directory does not exist.

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ ls 76wq3orfih
ls: cannot access '76wq3orfih': No such file or directory

- Tries to list `76wq3orfih` and redirects output to error.txt, but no output is captured.

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ ls 76wq3orfih > error.txt
```
- Lists contents of `Downloads`, showing `error.txt`

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ ls
'code_1.91.1-1720564633_amd64 (1).deb:Zone.Identifier'   error.txt
```
- Displays the first lines of `error.txt`, which is empty.

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ head error.txt
```
- Redirects error output of `ls 76wq3orfih` to `error.txt`

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ ls 76wq3orfih 2> error.txt
```

- Shows the error message stored in `error.txt`

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ head error.txt
ls: cannot access '76wq3orfih': No such file or directory
```

- Redirects both output and error of `ls 8270p98` to `output.txt`

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ ls 8270p98 > output.txt 2>&1
```

- Displays contents of `output.txt`, showing the error message

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ head output.txt
ls: cannot access '8270p98': No such file or directory
```

- Appends both output and error of `ls command_line/` to `output.txt`

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ ls command_line/ >> output.txt 2>&1
```

- Opens `output.txt` for viewing in the less pager.

```sh
andrewbavuels@the-Legionnaire:~/Downloads$ less output.txt
```

### Redirection Operators

| Operator | Function                                                                                      |
| -------- | --------------------------------------------------------------------------------------------- |
| `>`      | Redirects the output. By default, it redirects Standard Output (stdout).                     |
| `>>`     | Appends the output to the end of the specified file, preserving existing content.            |
| `2>`     | Redirects file descriptor 2 (Standard Error, stderr) to the specified file.                   |
| `2>&1`   | Redirects file descriptor 2 (stderr) to the same location as file descriptor 1 (stdout).       |
| `1>`     | Redirects file descriptor 1 (Standard Output, stdout) to the specified file.                  |
| `1>>`    | Appends Standard Output (stdout) to the end of the specified file.                            |
| `<`      | Redirects input from a file instead of from the keyboard.                                    |
| `<<`     | Reads input from the keyboard until a specific delimiter is encountered.                     |
| `<<<`    | Redirects a string to the input of a command.                                                |
| `|`      | Pipes the output of one command as input to another command.                                  |
| `|&`     | Pipes both Standard Output (stdout) and Standard Error (stderr) to another command.           |

As you have observed in practice, redirecting output and errors in the terminal is essential for **effective system management** and **debugging**. 

Capturing both standard output and errors helps with **precise problem diagnosis**, prevents information loss, and maintains useful logs, leading to more reliable system administration.

## 7. Pipe Operator Redirections

The pipe operator allows you to take the output of one command and pass it as input to another command. Here’s how it works with some useful commands:

#### Commands with Pipe Operator

- **Concatenate Text (cat)**

  Use `cat` to concatenate the output of multiple files. For example, you can combine the contents of `error.txt` and `output.txt`:

  ```sh
  cat error.txt output.txt
  ```
- **Create a File from Output (tee)**

Use `tee` to create a file from the output of a command. For example, save the long format listing of files to output.txt:

  ```sh
  ls -lh | tee output.txt
  ```
- **Organize Files with sort**

Use `sort` to alphabetically organize the output. For example, save the sorted list of files to `documents.txt`:

  ```sh
  ls -lh | sort | tee documents.txt | less
  ``` 
### Pipe Operator Commands Table

| Command | Function                                      |
| ------- | --------------------------------------------- |
| `sort`  | Organizes output alphabetically              |
| `cat`   | Concatenates multiple files or inputs        |
| `tee`   | Creates a file from input and displays it    |

### Bonus Commands Table

| Command                                              | Function                                           |
| ---------------------------------------------------- | -------------------------------------------------- |
| `cowsay "Hello World!"`                             | Prints "Hello World!" using `cowsay`.             |
| `sudo apt install cowsay`                           | Installs the `cowsay` program.                    |
| `sudo apt install lolcat`                           | Installs the `lolcat` program.                    |
| `echo "Hello World!" | lolcat`                      | Pipes "Hello World!" through `lolcat` for colorization. |
| `cowsay "Hello World!" | lolcat | tee cow.txt`      | Saves the output of `cowsay` piped through `lolcat` to `cow.txt` and displays it. |

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre$ cowsay "Hello World!" | lolcat
 ______________
< Hello World! >
 --------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

## 8. Chaining Commands with Shell Control Operators

Shell control operators are special symbols that allow you to chain commands together, streamline your workflow, and handle multiple tasks more efficiently.

### Commands in the Same Line (`;`)

The `;` operator allows you to run multiple commands sequentially on the same line. Each command runs regardless of the success or failure of the previous commands.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures$ ls; mkdir hi; cal
```
**Explanation:**

  - Lists the files in the current directory.
  - Creates a directory named "hi".
  - Prints the calendar for the current month.

```sh
'0. CyberpunkNomad (Viajes Inter)'  '3. VIVE COLOMBIA (viajesillos)'  'Camera Roll'   misarchivos.txt
'1. BARRANQUILLA'                   '4. SPECIAL GUESTS'                Screenshots
'2. BOGOTA'                          AuxVID                            desktop.ini
     July 2024
Su Mo Tu We Th Fr Sa
    1  2  3  4  5  6
 7  8  9 10 11 12 13
14 15 16 17 18 19 20
21 22 23 24 25 26 27
28 29 30 31

andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures$ ls
'0. CyberpunkNomad (Viajes Inter)'  '3. VIVE COLOMBIA (viajesillos)'  'Camera Roll'   hi
'1. BARRANQUILLA'                   '4. SPECIAL GUESTS'                Screenshots    misarchivos.txt
'2. BOGOTA'                          AuxVID                            desktop.ini
```
### Asynchronous Commands (&)
The `&` operator runs commands asynchronously, meaning they execute simultaneously in the background. This allows you to run multiple commands at the same time.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures$ ls & date & cal
[1] 11612
[2] 11613
     July 2024
Su Mo Tu We Th Fr Sa
    1  2  3  4  5  6
 7  8  9 10 11 12 13
14 15 16 17 18 19 20
21 22 23 24 25 26 27
28 29 30 31

andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures$ '0. CyberpunkNomad (Viajes Inter)'  '3. VIVE COLOMBIA (viajesillos)'  'Camera Roll'   hi
'1. BARRANQUILLA'                   '4. SPECIAL GUESTS'                Screenshots    misarchivos.txt
'2. BOGOTA'                          AuxVID                            desktop.ini
Sun Jul 28 13:58:17 CEST 2024
^C
[1]-  Done                    ls --color=auto
[2]+  Done                    date
```
**Explanation:**

  - `ls` lists the files in the directory..
  - `date` prints the current date and time.
  - `cal` prints the calendar for the current month.

### Conditional Commands (&& and ||)

- **Conditional AND (`&&`)**

The `&&` operator executes the next command only if the previous command was successful (i.e., returned an exit status of 0).

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures$ mkdir test && cd test
```
**Explanation:**

  - Creates a directory named "test".
  - Changes to the "test" directory only if the `mkdir` command was successful.

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures/test$ pwd
/mnt/c/Users/andre/Pictures/test
```
- **Conditional OR (`||`)**

The `||` operator executes the next command only if the previous command failed (i.e., returned a non-zero exit status).

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures/test$ cd uwhpwj || touch file.txt || echo "File created"
```

**Explanation:**

  - Attempts to change to the directory "uwhpwj". If it fails, creates a file named "file.txt".
  - If `cd` fails and `touch` also fails, prints "File created".

```sh
-bash: cd: uwhpwj: No such file or directory
file.txt
```
```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures/test$ cd hruhjwjh || echo "Folder changing"
```
**Explanation:**

  - Attempts to change to the directory "hruhjwjh". If it fails, prints "Folder changing".

```sh
-bash: cd: hruhjwjh: No such file or directory
Folder changing
```
### Operators Table

| Operator | Function                                                                |
| -------- | ----------------------------------------------------------------------- |
| `;`      | Executes commands sequentially, regardless of the previous command's success |
| `&`      | Executes commands asynchronously, allowing multiple commands to run simultaneously |
| `&&`     | Executes the next command only if the previous command succeeded       |
| `||`     | Executes the next command only if the previous command failed           |

### Commands Table

| Command | Function                                        |
| ------- | ----------------------------------------------- |
| `echo`  | Prints the message you specify                  |
| `cal`   | Prints a calendar with the current date         |
| `date`  | Prints the current date and time                |
| `pwd`   | Prints the current working directory            |
| `mkdir` | Creates a new directory                        |
| `ls`    | Lists files and directories in the current directory |
| `touch` | Creates an empty file                          |

```sh
andrewbavuels@the-Legionnaire:/mnt/c/Users/andre/Pictures/test$ cd ui748o3nr || touch file.txt && cowsay "Happy
 hacking!" | lolcat
-bash: cd: ui748o3nr: No such file or directory
 ________________
< Happy hacking! >
 ----------------
        \   ^__^
         \  (oo)\_______
            (__)\       )\/\
                ||----w |
                ||     ||
```

## 9. Permission Management

Permissions define what actions users can perform on files and directories in a Linux system. They are displayed using `ls -l`, where the first column shows permissions.

#### File Types
- `-` : Regular file (e.g., text, photo, video).
- `d` : Directory.
- `l` : Symbolic link.
- `b` : Block device (system-related files, e.g., disk info).

#### User Categories
- **Owner**: Creator of the file; highest authority.
- **Group**: Shared permissions for group members.
- **World**: All other users; lowest authority.

#### Permission Types
- `r` (readable): View contents.
- `w` (writable): Edit file content, name, or permissions.
- `x` (executable): Run as a program.

Permissions are listed in the order `rwx` or replaced with `-` if unavailable. Example:  
`drwxr-xr-x`  
- `d`: Directory.  
- **Owner**: `rwx` (read, write, execute).  
- **Group**: `r-x` (read, execute).  
- **World**: `r-x` (read, execute).

#### Octal Representation
Permissions are converted to octal using binary:  
- `rwx = 111 = 7`  
- `rw- = 110 = 6`  
- `r-- = 100 = 4`

Example: `rwxr-xr--`  
- **Owner**: `rwx = 7`.  
- **Group**: `r-x = 5`.  
- **World**: `r-- = 4`.  
- Octal: `754`.

<!-- #### Practice Exercises
Convert the following:
1. A directory: Owner (read, write), Group (write, execute), World (no permissions).
2. A symbolic link: Owner (all), Group & World (read only).
3. A regular file: Owner & Group (all), World (read, write).

Practice interpreting and modifying permissions in the terminal! -->

## 10. Modifying Permissions in the Terminal

Follow these steps to explore file permissions in Linux:

#### 1. Create a Directory and File

```sh
mkdir sandbox
cd sandbox/
> mytext.txt
cat > mytext.txt
```

Add text (Hello world from Holidata!) and view it:

```sh
cat mytext.txt
```
#### 2. Check Initial Permissions

```sh
ls -l
# Output: -rw-r--r-- 1 andrewbavuels andrewbavuels
```
#### 3. Change Permissions with `chmod`

- Add execution rights to all:

```sh
chmod 755 mytext.txt
ls -l
# Output: -rwxr-xr-x
```

- Remove read permission for the owner:

```sh
chmod u-r mytext.txt
ls -l
# Output: --wxr-xr-x
```
- Attempting to read results in:

```sh
cat mytext.txt
# Output: Permission denied
```
#### 4. Restore Permissions

- Add read permission back to the owner:

```sh
chmod u+r mytext.txt
ls -l
# Output: -rwxr-xr-x
cat mytext.txt
```
- Adjust multiple permissions:

```sh
chmod u-x,go=w mytext.txt
ls -l
# Output: -rw--w--w-
```
#### 5. Switch Users and Manage Permissions

- Check your current user and groups:

```sh
whoami
id
```

- Switch to root, create a file, and return:

```sh
su root
touch rootfile.txt
su andrewbavuels
ls -l
```
Observe ownership differences.

#### 6. Remove Files with Appropriate Permissions

- Attempt to remove `rootfile.txt` as a regular user:

```sh
rm rootfile.txt
# Output: Permission denied
```

- Use `sudo` to remove it:

```sh
sudo rm rootfile.txt
ls
# Output: mytext.txt
```

## 11. How to set environment variables

Environment variables are dynamic values that can affect the behavior of running processes on a computer. This guide will walk you through managing and using environment variables in Linux with practical examples from a real-world setup.

1. Viewing Current Environment Variables  
To view all environment variables in your system, use:

```sh
printenv
```
This will display a list of key-value pairs for all environment variables. For example:

```sh
SHELL=/bin/bash
HOME=/home/andrewbavuels
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```
Practical Example

```sh
andrewbavuels@the-Legionnaire:~$ printenv
...
HOME=/home/andrewbavuels
PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
```

Accessing Specific Environment Variables
To access a specific environment variable, use echo followed by the variable name prefixed with $:

```sh
echo $HOME
```
Example Output

```sh
/home/andrewbavuels
```
Navigating with Environment Variables
You can use environment variables directly in navigation commands. For example:
Navigate to the home directory:

```sh
cd $HOME
```
Navigate back:

```sh
cd -
```

Practical Workflow

```sh
andrewbavuels@the-Legionnaire:~$ cd $HOME
andrewbavuels@the-Legionnaire:~$ pwd
/home/andrewbavuels
```

Modifying the PATH Variable
The PATH variable defines the directories where your shell looks for executable files. You can add custom directories to PATH dynamically or permanently.
Temporary Modification
To temporarily add a directory to PATH:

```sh
export PATH=$PATH:/path/to/new/directory
```
Permanent Modification
To make the change permanent, edit your shell configuration file (e.g., .bashrc or .zshrc):

```sh
nano ~/.bashrc
```
Add this line:

```sh
export PATH=$PATH:/path/to/new/directory
```
Then apply the changes:

```sh
source ~/.bashrc
```
Creating a Symbolic Link to a Directory
A symbolic link (symlink) can simplify navigation by providing a shortcut to another directory.
Command

```sh
ln -s /path/to/target /path/to/link
```
Practical Example

Linking the cyberpunkNoMAD directory to the current directory:

```sh
ln -s /mnt/c/Users/andre/cyberpunkNoMAD cyberpunkNoMAD
cd cyberpunkNoMAD
```

Listing Directory Contents
To view detailed information about files and symbolic links in your home directory, use:

```sh
ls -la
```
Practical Example

```sh
andrewbavuels@the-Legionnaire:~$ ls -la
lrwxrwxrwx  1 andrewbavuels andrewbavuels         23 Jul 16 11:30  .aws -> /mnt/c/Users/andre/.aws
lrwxrwxrwx  1 andrewbavuels andrewbavuels         25 Jul 16 11:30  .azure -> /mnt/c/Users/andre/.azure
```

Practical Environment Variable Usage
View Current Directories in PATH

```sh
echo $PATH
```
Output Example

```sh
/home/andrewbavuels/.local/bin:/home/andrewbavuels/.nvm/versions/node/v20.15.1/bin:/usr/local/bin
```
Use Case
If a command is not recognized, ensure its executable's directory is included in your PATH.

Cleaning Up
If you no longer need a symbolic link or wish to reset an environment variable:
Remove a symlink:

```sh
rm symlink_name
```
Unset an environment variable (temporary):

```sh
unset VARIABLE_NAME
```
By mastering these commands, you'll efficiently manage your Linux environment, enabling smooth workflows and effective customizations.

## 12: Search Commands

In this chapter, we will go through search commands used in the terminal. The `find` command is a powerful tool for locating files and directories on your system based on various criteria.

### Commands Used in This Chapter

#### 1. `which` Command

The `which` command is used to find the location of executables in your system’s PATH.

```sh
andrewbavuels@the-Legionnaire:~/git_github$ which cd
andrewbavuels@the-Legionnaire:~/git_github$ type cd
cd is a shell builtin
andrewbavuels@the-Legionnaire:~/git_github$ which code
/mnt/c/Users/andre/AppData/Local/Programs/Microsoft VS Code/bin/code
```

- The `which` command finds the path of an executable. If it’s a shell builtin (like `cd`), it will indicate that.
- The example shows that `cd` is a shell builtin, while `code` is located in a specific directory.

#### 2. `find` Command

The `find` command is used to search for files and directories within a given directory.

**Example 1:** Searching for files named `file` in the current directory

```sh
andrewbavuels@the-Legionnaire:~/git_github$ find ./ -name file
```

**Example 2:** Searching for files named file in the home directory

```sh
andrewbavuels@the-Legionnaire:~/git_github$ find ~ -name file
/home/andrewbavuels/anaconda3/lib/python3.12/site-packages/spyder/images/file
^[[A^[[A/home/andrewbavuels/anaconda3/pkgs/spyder-5.5.1-py312h06a4308_0/lib/python3.12/site-packages/spyder/images/file
^[[B^[[B^[[B^[[B^[[B^[[B^[[A^[[Aq^X/home/andrewbavuels/.eclipse/org.jkiss.dbeaver.product_23.0.5_302967072_linux_gtk_x86_64/configuration/org.eclipse.osgi/255/0/.cp/icons/file
^C
```

- This command searches for a file named `file` in your home directory (`~`).
- The output shows the paths where the file is located.

**Example 3:** Searching for `.txt` files in the home directory and viewing them with `less`

```sh
andrewbavuels@the-Legionnaire:~/git_github$ find ~ -name *.txt
/home/andrewbavuels/error.txt
/home/andrewbavuels/.nvm/versions/node/v20.15.1/lib/node_modules/npm/node_modules/emoji-regex/LICENSE-MIT.txt
...
andrewbavuels@the-Legionnaire:~/git_github$ find ~ -name *.txt | less
```

This command finds all .txt files in the home directory. Piping the output to less allows you to scroll through it easily.

**Example 4:** Searching for directories named Downloads

```sh
andrewbavuels@the-Legionnaire:~/git_github$ find ~ -type d -name Downloads
/home/andrewbavuels/Downloads
```

This command searches for directories (-type d) named Downloads in the home directory.

**Example 5:** Searching for .log files in the home directory

```sh
andrewbavuels@the-Legionnaire:~/git_github$ find ~ -type f -name *.log
...
/home/andrewbavuels/.vscode-server/data/logs/20241202T150614/exthost1/vscode.github/GitHub.log
```

This command searches for files (-type f) with a .log extension.

**Example 6:** Searching for files larger than 20MB

```sh
andrewbavuels@the-Legionnaire:~/git_github$ find ~ -size 20M
/home/andrewbavuels/.npm/_cacache/content-v2/sha512/bb/07/48ebbc4e1513024bae99910f2ad4386f3cc499ee593d65f1c6072fede021f6f54727ee3a8746b6addcd06ee03397e959c68a09e189329677469ac2b3cb8e
/home/andrewbavuels/anaconda3/pkgs/panel-1.4.4-py312h06a4308_0.conda
...
```

This command finds all files that are larger than 20MB.

**Example 7:** Searching for files larger than 5MB

```sh
andrewbavuels@the-Legionnaire:~/git_github$ find ~ -size 5M
/home/andrewbavuels/.npm/_cacache/content-v2/sha512/c9/84/8d0dcebd2172fa73312747fed00c7e2bc036a364c7bd0bff69d322ff5772dcbc92b86a3930095ebab03baeff930fbce53bcad2469eca8d43bfdfbc3d269d
...
```

This command finds all files larger than 5MB.

### Practice Exercise

#### Task:
- Find files greater than 100MB, with a maximum depth of 4, that start with the letter "d".
- Find files with the .pdf extension, with a minimum depth of 2.
- Find empty directories starting with the letter "A", with a maximum depth of 5.
- Find files that contain the letter "j" and are larger than 1 byte. Save the output to a file named `LosArchivosJ.txt`. Once completed, print the message "Comando terminado con éxito".

#### Solutions:

```sh
# 1. Find files greater than 100MB, with a depth of 4, that start with "d"
find ~ -maxdepth 4 -type f -name 'd*' -size +100M

# 2. Find .pdf files with a minimum depth of 2
find ~ -mindepth 2 -type f -name "*.pdf"

# 3. Find empty directories starting with "A", with a depth of 5
find ~ -maxdepth 5 -type d -name "A*" -empty

# 4. Find files containing the letter "j" and greater than 1 byte, save to a file and print message
find ~ -type f -name "*j*" -size +1b > LosArchivosJ.txt
echo "Comando terminado con éxito"
```

The first command finds all files greater than 100MB that start with "d" within a maximum depth of 4 directories.
The second command finds all .pdf files with at least 2 directory levels.
The third command searches for empty directories starting with "A" within a depth of 5.
The fourth command finds files with the letter "j" and a size greater than 1 byte, saves the results in `LosArchivosJ.txt`, and prints a success message.

### Summary

The `find` command is versatile and can be used for a variety of search operations based on criteria like file type, size, name, depth, and more. Mastering this command allows for more efficient navigation and management of files and directories on your system.

## 13. Using the grep command

Explore the `grep` command in Linux to search for specific text within files. Here's how to work with a file named `movies.csv`.

#### 1. Listing Files

First, we list the files to confirm that `movies.csv` is present:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ ls -lh
total 20M
-rw-r--r-- 1 andrewbavuels andrewbavuels 1.1M Dec  3 12:13  Content.docx
-rw-r--r-- 1 andrewbavuels andrewbavuels    0 Jul 17 11:59  GITS.gif:Zone.Identifier
drwxr-xr-x 2 andrewbavuels andrewbavuels 4.0K Jul 17 13:43  Images
-rw-r--r-- 1 andrewbavuels andrewbavuels  35K Jul 17 10:47  LICENSE
-rw-r--r-- 1 andrewbavuels andrewbavuels  39K Dec  3 13:22  README.md
-rw-r--r-- 1 andrewbavuels andrewbavuels 9.2M Aug 22 11:26  Welcome.mp4
-rw-r--r-- 1 andrewbavuels andrewbavuels 117K Jul 17 07:50  command-line-cheat-sheet.pdf
-rw-r--r-- 1 andrewbavuels andrewbavuels    0 Jul 17 07:50  command-line-cheat-sheet.pdf:Zone.Identifier
-rw-r--r-- 1 andrewbavuels andrewbavuels 467K Dec  3 13:23  movies.csv
```

We will focus on `movies.csv`.

#### 2. Searching for a Specific Term

To search for the term "Towers" in the file, use:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ grep Towers movies.csv
108583,Fawlty Towers (1975,Comedy,-1980,1,54
5952,"Lord of the Rings: The Two Towers, The",Adventure|Fantasy,2002,4,81
```

This shows all lines containing the word "Towers."

#### 3. Case-insensitive Search

You can search without considering case by using the `-i` flag:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ grep -i the movies.csv
32898,"Trip to the Moon, A (Voyage dans la lune, Le)",Action|Adventure|Fantasy|Sci-Fi,1902,7,80
7065,"Birth of a Nation, The",Drama|War,1915,6,92
7243,Intolerance: Love's Struggle Throughout the Ages,Drama,1915,4,82
```

This finds all instances of the word "the," regardless of case.

#### 4. Count Occurrences

To count how many lines contain a specific term, use `-c`:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ grep -c the movies.csv
1013
```

To count case-insensitively:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ grep -ci the movies.csv
2912
```

#### 5. Exclude Lines with a Specific Term

To exclude lines containing a certain term, use the `-v` flag:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ grep -vi towers movies.csv
8572,"Littlest Rebel, The",Children|Drama,1935,1,61
52913,Sylvia Scarlett,Comedy|Drama|Romance,1935,4,64
87383,Curly Top,Children|Musical|Romance,1934,5,91
91286,"Little Colonel, The",Children|Comedy|Crime|Drama,1934,3,54
```

This excludes lines containing "towers" (case-insensitive).

#### 6. Redirect Output to a New File

You can redirect the output of the previous search to a new file:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ grep -vi towers movies.csv > with_no_towers.txt
```

Check the contents of `with_no_towers.txt`:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ cat with_no_towers.txt
8572,"Littlest Rebel, The",Children|Drama,1935,1,61
52913,Sylvia Scarlett,Comedy|Drama|Romance,1935,4,64
87383,Curly Top,Children|Musical|Romance,1934,5,91
91286,"Little Colonel, The",Children|Comedy|Crime|Drama,1934,3,54
99085,Our Little Girl,Comedy|Drama|Romance,1934,6,67
947,My Man Godfrey,Comedy|Romance,1935,5,91
...
```

#### 7. Word and Line Count

You can count the words and lines in `movies.csv` using `wc`:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ wc movies.csv
  9126  30006 477779 movies.csv
```

- `-l` counts lines:
  
```sh
andrewbavuels@the-Legionnaire:~/command_line$ wc -l movies.csv
9126 movies.csv
```

- `-w` counts words:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ wc -w movies.csv
30006 movies.csv
```

- `-c` counts bytes:

```sh
andrewbavuels@the-Legionnaire:~/command_line$ wc -c movies.csv
477779 movies.csv
```

## 14. Compressing tar and zip files

### Summary

This section demonstrates how to create and extract compressed files using `tar` and `zip` utilities.

1. **Create a `.tar` file**:
    - `tar -cvf ToCompress.tar ToCompress/` creates a `.tar` archive of the `ToCompress` directory.

2. **Create a `.tar.gz` file**:
    - `tar -cvzf ToCompress.tar.gz ToCompress/` creates a compressed `.tar.gz` file.

3. **Extract `.tar` file**:
    - `tar -xzvf ToCompress.tar.gz` extracts the `.tar.gz` archive.

4. **Create a `.zip` file**:
    - `zip -r ToCompressInZip.zip ToCompress` compresses the `ToCompress` directory into a `.zip` file.

5. **Extract `.zip` file**:
    - `unzip ToCompressInZip.zip` extracts the `.zip` file contents.

### Explanation

- **`tar`**: Used for archiving, with optional compression (`-z` for gzip). The `.tar.gz` format is common on Unix-like systems.
- **`zip`**: Creates compressed `.zip` archives, widely used across platforms.

### Code Example

```bash
andrewbavuels@the-Legionnaire:~/command_line$ zip -r ToCompressInZip.zip ToCompress
  adding: ToCompress/ (stored 0%)
  adding: ToCompress/file3 (stored 0%)
  adding: ToCompress/file2 (stored 0%)
  adding: ToCompress/file (stored 0%)

andrewbavuels@the-Legionnaire:~/command_line$ ls
ToCompressInZip.zip

andrewbavuels@the-Legionnaire:~/command_line$ unzip ToCompressInZip.zip
Archive:  ToCompressInZip.zip
 extracting: ToCompress/file3
 extracting: ToCompress/file2
 extracting: ToCompress/file
```
### Key Takeaways

- Use `tar` for archiving and compression, especially on Unix systems.
- Use `zip` for cross-platform file compression.

## 15. Process Management

This section covers managing processes in Linux using commands like `ps`, `top`, `kill`, and background tasks.

1. **View running processes**:
    - `ps` shows the current processes running in the terminal. It lists the process ID (PID), terminal, time used, and command.

2. **Run a command in the background**:
    - Using `&` to run a command in the background. For example, `cat & ls` runs `cat` in the background and immediately returns the prompt for `ls`.

3. **Check the process list**:
    - `ps` will show the list of running processes. You can see background jobs (e.g., `cat` processes running in the background).

4. **Stop a process**:
    - You can stop a running process using the `kill` command with the process ID (PID). For example, `kill 9979` will terminate the process with PID 9979.

5. **Monitor processes in real time**:
    - `top` shows the real-time resource usage of processes on the system, including CPU and memory usage.

### Explanation

- **`ps`**: Displays a snapshot of running processes.
- **`&`**: Runs a command in the background, freeing up the terminal for other commands.
- **`kill`**: Terminates a process by its PID.
- **`top`**: Shows dynamic, real-time information about system processes, memory usage, and CPU usage.

### Code Example

```bash
andrewbavuels@the-Legionnaire:~/command_line$ ps
  PID TTY          TIME CMD
   10 pts/0    00:00:00 bash
  9834 pts/0    00:00:00 ps

andrewbavuels@the-Legionnaire:~/command_line$ cat & ls
[1] 9979
Content.docx              command-line-cheat-sheet.pdf
GITS.gif:Zone.Identifier  command-line-cheat-sheet.pdf:Zone.Identifier
Images                    index.html
LICENSE                   movies.csv
README.md                 movies_afffe2e6-a55c-47f0-8895-9d37c9cd9eb8.csv:Zone.Identifier
ToCompress                outFile.gif
ToCompress.tar            sandbox
ToCompress.tar.gz         slides.pdf
ToCompressInZip.zip       with_no_towers.txt
Welcome.mp4

andrewbavuels@the-Legionnaire:~/command_line$ ps
  PID TTY          TIME CMD
   10 pts/0    00:00:00 bash
  9979 pts/0    00:00:00 cat
  9999 pts/0    00:00:00 ps

[1]+  Stopped                 cat
andrewbavuels@the-Legionnaire:~/command_line$ kill 9979
andrewbavuels@the-Legionnaire:~/command_line$ ps
  PID TTY          TIME CMD
   10 pts/0    00:00:00 bash
  9979 pts/0    00:00:00 cat
  10054 pts/0    00:00:00 ps

andrewbavuels@the-Legionnaire:~/command_line$ top
top - 15:54:29 up 56 min,  0 users,  load average: 0.06, 0.07, 0.02
Tasks:  31 total,   1 running,  28 sleeping,   2 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.1 sy,  0.0 ni, 99.7 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   7870.3 total,   7058.8 free,    657.1 used,    154.5 buff/cache
MiB Swap:   2048.0 total,   2048.0 free,      0.0 used.   7006.2 avail Mem
```

### Key Takeaways
- Use `ps` to monitor current processes and their resource usage.
- Background jobs are managed with `&`, and can be viewed or controlled using `ps`.
- Use `kill` to stop unwanted processes.
- `top` provides a dynamic and real-time view of the system’s processes and resources.

## 16. Text Editors in the Terminal

This section demonstrates using terminal-based text editors, focusing on Vim. Vim is a powerful and widely-used text editor for creating and modifying files directly in the terminal.

### Key Commands in Vim

1. **Launch Vim**:
   - Open Vim by typing `vim` followed by the file name:
     ```sh
     vim index.html
     ```

2. **Insert Mode**:
   - Press `I` to enter **INSERT** mode, where you can edit the file content.
     ```html
     <div>Hello world</div>
     ```

3. **Exit Insert Mode**:
   - Press `Esc` to return to command mode.

4. **Delete Content**:
   - In command mode, press `dd` to delete a line.

5. **Save and Exit**:
   - In command mode, type `:wq` to save changes and exit.
   - To save without quitting, type `:w`.
   - To quit without saving, type `:q!`.

6. **Force Save and Quit**:
   - Use `:wq!` to force save and exit.

---

### Workflow Example

#### Open a File and Edit

1. Open an HTML file for editing:
   ```sh
   vim index.html
   ```


2. Enter INSERT mode by pressing `I` and add content:

   ```sh
   <div>Hello world</div>
   ```

3. Exit INSERT mode by pressing `Esc`


4. Save the changes and quit Vim:

   ```sh
   :wq
   ```


5. Verify the file content:

   ```sh
   cat index.html
    <div>Hello world</div>
   ```

### Useful Tips

- Undo: Press `u` in command mode to undo the last action.
- Redo: Press `Ctrl + R` in command mode to redo an undone action.
- Search: Type `/` followed by the text to search for and press `Enter`. Navigate matches with `n` (next) or `N` (previous).

## 17. Customize the command terminal (in progress...)
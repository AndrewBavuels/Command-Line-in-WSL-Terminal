# Command Line in WSL Terminal

## (In working progress..)

### Table of Contents

1. [What is the terminal?](#1-what-is-the-terminal)
2. [Getting to know the file system through the terminal](#2-getting-to-know-the-file-system-through-the-terminal)
3. [Manipulating files and folders](#3-manipulating-files-and-folders)
4. [Exploring the content of our files](#4-exploring-the-content-of-our-files)
5. [Wildcards](#5-Wildcards)

---

## 1. What is the terminal?

- The terminal is an indispensable tool that anyone in technology must know 👀. It is important because:
  1. **It gives you flexibility 📏.** With just a few commands, you can do a lot.
  2. **It is much faster than a graphical interface 💻.**
  3. **It is your only option if there is no interface 😆,** such as for configuring a remote server.
  4. **You can invoke daemons 👿.** You need to be careful with commands, such as **remove.**

- Specifically, the terminal is a very simple graphical interface that simulates a command line:
  1. **Terminal:** Window that shows the prompt.
  2. **Shell (command line):** Program that executes commands. There are various types of shells, but they all serve the same purpose. The most common ones are the bash shell or Z shell. In this course, we will use the former 🍎.

- **It is important to start using Linux 😟.**

- A command is a program that can be executed from the terminal.

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

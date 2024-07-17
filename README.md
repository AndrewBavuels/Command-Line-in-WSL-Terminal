# Command Line in WSL Terminal

## What is the terminal?

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


## Getting to know the file system through the terminal

Below, I am listing the contents of the **root directory,** showing various system directories and files, with one of the command series that I am going to show you as follows:

```sh
ls # Lists the contents of a directory.

andrewbavuels@the-Legionnaire:/$ ls
Docker  dev   init   lib64       media             mnt   proyectoPersonal  sbin  tmp  wslcdeaCh  wsloOFoIg
bin     etc   lib    libx32      miniconda.html    opt   root              srv   usr  wsleaooND
boot    home  lib32  lost+found  miniconda.html.1  proc  run               sys   var  wsllHHkkc
```
The folder **'/'** after my username (andrewbavuels@the-Legionnaire:), is called the **root directory.** It is the top-most directory in a Unix or Linux file system hierarchy and contains all other files and directories on the system.
```sh
cd # Changes the current directory.

andrewbavuels@the-Legionnaire:~/python$ cd pentaho/
andrewbavuels@the-Legionnaire:~/python/pentaho$
```
```sh
ls -l # Lists the contents of a directory in long format, showing detailed information about each file and directory, such as permissions, owner, size, and modification date.
```
```sh

ls -h # Lists the contents of a directory with file sizes in human-readable format, such as KB, MB, or GB.

andrewbavuels@the-Legionnaire:~/python/pentaho$ ls -h
hs_codes.csv
hs_codes_67d0ca02-86f0-4829-8568-389ab67a38e5.csv:Zone.Identifier
pentaho-etl
template_etl.ipynb
template_etl_oec_9d24a368-c162-49d7-a1e7-d05a278cd880.ipynb:Zone.Identifier
```
```sh
clear (or crtl+l) # Clears the terminal screen, removing all previous commands and outputs from view.

andrewbavuels@the-Legionnaire:/$ clear
```
```sh
cd .. # Changes the current directory to the parent directory.

andrewbavuels@the-Legionnaire:~/python/pentaho$ cd ..
andrewbavuels@the-Legionnaire:~/python$
```
```sh
cd ~ # Changes the current directory to your home directory.

andrewbavuels@the-Legionnaire:~$ cd ~
andrewbavuels@the-Legionnaire:~$
```
```sh
pwd # Prints the current working directory.

andrewbavuels@the-Legionnaire:~$ pwd
/home/andrewbavuels
```
```sh

cd . # Refers to the current directory, although if you are as:

cd ./['furtherfolder'] # This command changes the current directory to a subdirectory within the relative path

andrewbavuels@the-Legionnaire:~$ cd ./command_line
andrewbavuels@the-Legionnaire:~/command_line$
```
```sh 
ls -la #Lists all contents of a directory in long format, including hidden files (files starting with a dot .).

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

```sh 
tree # it's a useful tool for visualizing directory structures.

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

## Manipulating files and folders

I want to take advantage of this point to create an exclusive folder for the readme...

```sh
mkdir # Creates a new directory.

andrewbavuels@the-Legionnaire:~/command_line$ mkdir README
andrewbavuels@the-Legionnaire:~/command_line$
```
**Suggestion:** For easy manipulation, avoid spaces when naming the file/folder. E.G. Instead of "READ ME", name it like README (no spaces).

```sh
touch # Creates an empty file or updates the timestamp of an existing file.

andrewbavuels@the-Legionnaire:~/command_line$ touch example.txt
andrewbavuels@the-Legionnaire:~/command_line$ ls
 Content.docx               README.md                                      example.txt
```

```sh
cp file1 file2 # Copies files or directories to file2 or directory2

andrewbavuels@the-Legionnaire:~/command_line$ cp example.txt example_2.txt
```
```sh
mv # Moves or renames files or directories.

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

```sh
rm # WARNING!!!! Removes files or directories (even Hard drives)

andrewbavuels@the-Legionnaire:~/command_line$ rm README.md example_1 example_2.txt 'Recording 2024-07-17 122242.mp4'
```
```sh
andrewbavuels@the-Legionnaire:~/command_line/README$ ls
README.md
andrewbavuels@the-Legionnaire:~/command_line/README$ git add .
andrewbavuels@the-Legionnaire:~/command_line/README$ git status
On branch main
Your branch is ahead of 'origin/main' by 1 commit.
  (use "git push" to publish your local commits)

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   README.md
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
# Lab Report #1
## Jason Chang / jsc008@ucsd.edu
## CSE15L / Section A01
## April 10, 2023

Below is lab report #1 - writing a blog post about remote access - logging into a course-specific account on `ieng6`.

# Installing VSCode

![Installing VSCode](https://raw.githubusercontent.com/JC01010/cse15l-lab-reports/main/part1.png)

 1. Go to https://code.visualstudio.com/ and install VSCode. Select the proper option for macOS or Windows.

# Remotely Connecting
![Remotely Connecting](https://raw.githubusercontent.com/JC01010/cse15l-lab-reports/main/part2.png)

First, reset your course-specific account.
1. Go to https://sdacs.ucsd.edu/~icc/index.php to lookup your course-specific account. You will need your UCSD username and PID.
 2. Click the button for your CSE 15L course-specific account. It starts with `cs15lsp23`. Copy this username.
 3. Go to https://password.ucsd.edu/ and enter the course-specific username above.
 4. Reset the password.

Then, navigate to VS Code.
1. Type `ssh cs15lsp23XX.ieng6.ucsd.edu` into the Terminal. Replace `XX` with the letters in your username. 
2. Enter in your password that was reset from above.
3. If prompted and asked if you want to continue connecting, type "yes".
4. If all done correctly, you will see `[cs15lsp23ac@ieng6-201]:~:1$` in the command line appear.

# Trying Some Commands

![Trying Some Commands](https://raw.githubusercontent.com/JC01010/cse15l-lab-reports/main/part3.png)

To get used to the command line, the following commands were tried:
1. `cd`. `cd` is used to change directories.
2. `ls`. `ls` lists out all folders/files in your current directory.
3. `ls -a`. `ls -a` lists all hidden folders/files (that start with `.`) in your current directory.

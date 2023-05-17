# Lab Report #4
## Jason Chang / jsc008@ucsd.edu
## CSE15L / Section A01
## May 22, 2023

Below is lab report #4 - git (Week 7-8).

# 4. Login to ieng6
First, I typed `ssh cs15lsp23XX@ieng6.ucsd.edu<enter>` to ssh into my `ieng6` account. Then, I typed `<Password><enter>`to enter my password. I am now logged in.

![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20155531.png?raw=true)

# 5. Cloning from Fork
First, I forked the repository from [https://github.com/ucsd-cse15l-s23/lab7/](https://github.com/ucsd-cse15l-s23/lab7/) by clicking the top right "fork" button. Then, I typed `git clone https://github.com/JC01010/lab7.git<enter>` to clone the repository.

![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20154443.png?raw=true)

# 6. Running Tests (Failed)
I ran the test by running the `test.sh` file, which contained commands to run the `ListExamples.java` file. The command used was `bash test.sh<enter>`.
![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20153405.png?raw=true)


# 7. Editing the Code
I entered the file by typing `vim ListExamples.java<enter>`. Then, I typed the command `42j6lciwindex2<esc><esc>:wq<enter>`.

Breaking the command down, `42j` goes down 42 lines to the 43rd line, and 	`6l` goes 6 characters right to the start of `index1`, which is supposed to be changed to `index2`. Then, `ciw` changes the word selected, of which `index2` is typed to replace the previous string. I pressed `<esc>` twice in order to escape the typing interface, `:w` to save the file, and `q` to quit, and `<enter>` to finish up the command.

![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20155808.png?raw=true)

# 8. Running Tests (Passed)
I ran the test by running the `test.sh` file, which contained commands to run the `ListExamples.java` file. The command used was `bash test.sh<enter>`.

![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20153338.png?raw=true)

# 9. Commit and Push
First, I typed `git add .<enter>` to add the change to the working directory. Then, I typed `git commit -m "Fixed index1 to index2"<enter>` to commit with the message "Fixed index1 to index2". Lastly, I typed `git push<enter>` to push the change.

Git add all:
![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20155955.png?raw=true)

Git commit, with message:
![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20160026.png?raw=true)

Git Push:
![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/Screenshot%202023-05-17%20160045.png?raw=true)

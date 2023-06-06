# Lab Report #5
## Jason Chang / jsc008@ucsd.edu
## CSE15L / Section A01
## June 5th, 2023

Below is lab report #5 - debugging (Week 9-10).


# Part 1. Debugging Scenario
## EdStem Post
**What environment are you using (computer, operating system, web browser, terminal/editor, and so on)?**
I am running it on a Dell XPS w/ Windows 11. The software I'm using is VSCode.

**Detail the symptom you're seeing. Be specific; include both what you're seeing and what you expected to see instead. Screenshots are great, copy-pasted terminal output is also great. Avoid saying “it doesn't work”.**
![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/cse15llab1_1.png?raw=true)
Below is my bug that I am having trouble fixing. I ran the command based off of the wavelet lab, but it is tossing an error. Specifically, it says that it can't handle its superinterface URLHandler. I believe it is something to do with how java handles running the file.

**Detail the failure-inducing input and context. That might mean any or all of the command you're running, a test case, command-line arguments, working directory, even the last few commands you ran. Do your best to provide as much context as you can.**
The input is `java NumberServer.java Server.java`. I an running the commands provided in Week 2's lab.

## TA Response
Read the command in week 2's lab carefully. When running the java command, what is the `.java` file that you are running it against? Are you running `NumberServer.java` with the `Server.java` program, or vice versa?
## Terminal Output
Thank you! I misread the command and swapped the two. I should have run `Server.java` with `NumberServer.java` as the input.
![enter image description here](https://github.com/JC01010/cse15l-lab-reports/blob/main/cse15llab1_2.png?raw=true)
## Setup
- Fork [github.com/ucsd-cse15l-f22/wavelet](https://github.com/ucsd-cse15l-f22/wavelet) and navigate to `/wavelet`.
- The contents from the forked repository are unmodified.
- The input is `java NumberServer.java Server.java`.
- To fix the bug, switch `NumberServer.java` and `Server.java` in the command.

# Part 2. Reflection
Through CSE 15L, I've learned how to debug and fix errors in a more algorithmic manner. Previously, it was easy to guess and check my way through PAs in CSE 11 and CSE 12. However, I've learned to read each line carefully to determine what could be the cause of the error. In addition, I've developed a sense of how to use the terminal to my advantage, making tedious tasks faster and scripting things in the command line.

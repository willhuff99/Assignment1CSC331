## Student Name:

# Lab 1: Introduction to XV6 (10 points)

The goal of this lab is to write your first custom user-space program for xv6, add it to the file system, and run it inside the xv6 shell.

---

## Prerequisites

You should already have:
- Cloned and built xv6-riscv repository
- Successfully run `make qemu`

1. Task 1: Write your `hello.c` program

Use the Code browser, create a file called hello.c inside the user directory of the xv6-riscv repository with the following contents

~~~c
// hello.c - your first xv6 user program
#include "kernel/types.h"
#include "user/user.h"

int main() {
  printf("Hello from xv6!\n");
  exit(0);
}
~~~


2. Task 2: Register the program in the build

Use the Code browser, open the Makefile file in the root of the xv6 repo and look for the line that starts with: `UPROGS=\  `
Add hello to the list as follows

~~~c
UPROGS=\
  _cat\
  _echo\
  _hello\
  _init\
  ...
~~~

Note: The underscore `_` prefix tells the build system to include the `user/hello.c` binary in the file system image.

3. Task 3: Rebuild and Run xv6

Back in the root directory, rebuild and launch xv6

~~~bash
cd ~/xv6-riscv
make
make clean
make qemu
~~~

Wait for the xv6 shell prompt ($) to appear.

4. Task 4: Run your program Inside xv6

At the shell prompt, run the following commands

~~~bash
ls
hello
~~~


- Take one screenshot showing the output of ls with all the available xv6 commands, including hello.
- Take one screenshot showing the output of running hello.

5. Task 5: Explore modifications
- Edit `hello.c` to display a self introduction line with your name.
- Rebuild and rerun xv6.
- Run hello and take one screenshot showing the new output.

---

6. Technical Report

You are to create a single `report.md` file in this repository that contains 
  - a statement acknowledging that you have completed the lab and
  - the three screenshots as specified in Step 4 and 5.

You can follow [this guide](https://www.baeldung.com/ops/github-readme-insert-image) to see how to insert pictures into a `.md` file. 

---

## Submission:

- Add your name to the top of this README.md file, and also make sure that report.md contains your name. 
- Submit the link to this repository to D2L. 


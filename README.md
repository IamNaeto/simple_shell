# 0x16. C - Simple Shell

```sh
     _____       _                     __    _____ _          _ _
    / ____|     | |                   / _|  / ____| |        | | |
   | |  __  __ _| |_ ___  ___    ___ | |_  | (___ | |__   ___| | |
   | | |_ |/ _` | __/ _ \/ __|  / _ \|  _|  \___ \| '_ \ / _ \ | |
   | |__| | (_| | ||  __/\__ \ | (_) | |    ____) | | | |  __/ | |
    \_____|\__,_|\__\___||___/  \___/|_|   |_____/|_| |_|\___|_|_|
```
![image](https://user-images.githubusercontent.com/105589308/201345810-e5b660eb-873b-47c0-a7ab-90b649007c3c.png)
<details>
<summary>The Gates of Shell by Spencer Cheng, featuring Julien Barbier</summary>
<img src="https://user-images.githubusercontent.com/29776892/129798799-6f730688-8728-49ed-b01b-13bec0fa2896.jpeg">
</details>

## Resource

- [Unix shell](https://en.wikipedia.org/wiki/Unix_shell)
- [Thompson shell](https://en.wikipedia.org/wiki/Thompson_shell)
- [Ken Thompson](https://en.wikipedia.org/wiki/Ken_Thompson)
- [Everything you need to know to start coding your own shell](https://www.notion.so/C-Programming-f13cdb9661db464f8ea326c5a2654e8e)

---

## Description

In this project we are tasked with creating our own simple UNIX command interpreter. The program must have the exact same output as sh (/bin/sh) as well as the exact same error output. The only difference is when you print an error, the name of the program must be equivalent to your argv[0].

---

## Instructions

* Compiling the program:
`gcc -Wall -Werror -Wextra -pedantic *.c -o hsh`

* Interactive mode:
```
$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$
```

* Non-interactie mode:
```
$ echo "/bin/ls" | ./hsh
hsh main.c shell.c test_ls_2
$
$ cat test_ls_2
/bin/ls
/bin/ls
$
$ cat test_ls_2 | ./hsh
hsh main.c shell.c test_ls_2
hsh main.c shell.c test_ls_2
$
```
---

## Example

![example](https://media.giphy.com/media/cC9jj6fr8m5SZ56Z2l/giphy.gif)

---

## Files

File|Description
---|---
[main.c](./main.c)|entry point for shell
[shell.c](./shell.c)|executes the shell
[shell.h](./shell.h)|header
[builtins.c](./builtins.c)|built-in functions
[helpers.c](./helpers.c)|helper functions
[extraneous.c](./extraneous.c)|more helper functions
[_getenv.c](./_getenv.c)|gets inputted env
[search_cwd.c](./search_cwd.c)|gets current working dir
[find_path.c](./find_path.c)|finds PATH
[bridge.c](./bridge.c)|checks if builtin or not
[execute.c](./execute.c)|executes builtin or binary
[man_1_simple_shell](./man_1_simple_shell)|man page

---

## Project Requirements
- All your files will be compiled on Ubuntu 14.04 LTS
- Your C programs and functions will be compiled with gcc 4.8.4 using the flags `-Wall -Werror -Wextra and -pedantic`
- All your files should end with a new line
- A README.md file, at the root of the folder of the project is mandatory
- Your code should use the Betty style. It will be checked using [betty-style.pl](https://github.com/holbertonschool/Betty/blob/master/betty-style.pl) and [betty-doc.pl](https://github.com/holbertonschool/Betty/blob/master/betty-doc.pl)
- No more than 5 functions per file
- All your header files should be include guarded
- Use system calls only when you need to

---

## Tasks

### 0. README, man, AUTHORS
A
* Write a (README)[./README.md]
* Write a (man)[./man_1_simple_shell] for your shell.
* You should have an (AUTHORS)[./AUTHORS] file at the root of your repository, listing all individuals having contributed content to the repository.

### 1. Betty would be proud
* Write a beautiful code that passes the Betty checks

### 2. Simple shell 0.1
* Write a UNIX command line interpreter.
* Your Shell should:
	- Display a prompt and wait for the user to type a command. A command line always ends with a new line.
	- The prompt is displayed again each time a command has been executed.
	- The command lines are simple, no semicolons, no pipes, no redirections or any other advanced features.
	- The command lines are made only of one word. No arguments will be passed to programs.
	- If an executable cannot be found, print an error message and display the prompt again.
A
	- Handle errors.
	- You have to handle the "end of file" condition (Ctrl+D)

### 3. Simple shell 0.2
A
* Handle command lines with arguments

### 4. Simple shell 0.3
* Handle the PATH

### 5. Simple shell 0.4
* Implement the exit built-in, that exits the shell
* Usage: exit
* You dont have to handle any argument to the built-in exit

### 6. Simple shell 1.0
* Implement the env built-in, that prints the current environment

### 7. What happens when you type ls -l in the shell
* Blog:
A
	- [Medium](https://medium.com/@antisyllogism/what-happens-when-you-type-ls-l-in-the-shell-21a089cf0eb4)

---

<details>
<summary>List of allowed functions and system calls</summary>

+ `access` (man 2 access)
+ `chdir` (man 2 chdir)
+ `close` (man 2 close)
+ `closedir` (man 3 closedir)
+ `execve` (man 2 execve)
+ `exit` (man 3 exit)
B
+ `\_exit` (man 2 \_exit)
+ `fflush` (man 3 fflush)
+ `fork` (man 2 fork)
B
+ `free`(man 3 free)
+ `getcwd` (man 3 getcwd)
+ `getline` (man 3 getline)
+ `getpid` (man 2 getpid)
+ `isatty` (man 3 isatty)
+ `kill` (man 2 kill)
+ `malloc` (man 3 malloc)
+ `open` (man 2 open)
+ `opendir` (man 3 opendir)
+ `perror` (man 3 perror)
+ `read` (man 2 read)
+ `readdir` (man 3 readdir)
+ `signal` (man 2 signal)
+ `stat` (\_\_xstat) (man 2 stat)
+ `lstat` (\_\_lxstat) (man 2 lstat)
+ `fstat` (\_\_fxstat) (man 2 fstat)
+ `strtok` (man 3 strtok)
+ `wait` (man 2 wait)
+ `waitpid` (man 2 waitpid)
+ `wait3` (man 2 wait3)
+ `wait4` (man 2 wait4)
+ `write` (man 2 write)

</details>

<details>
<summary>The shell will be compiled this way:</summary>
<pre>$ gcc -Wall -Werror -Wextra -pedantic -std=gnu89 \*.c -o hsh</pre>
</details>

## Output

- Unless specified otherwise, your program must have the exact same output as `sh` (`/bin/sh`) as well as the exact same error output.
- The only difference is when you print an error, the name of the program must be equivalent to your `argv[0]` (see below)

<details>
     <summary>Example of error with sh:</summary>
<pre>$ echo "qwerty" | /bin/sh<br>/bin/sh: 1: qwerty: not found<br>$ echo "qwerty" | /bin/../bin/sh<br>/bin/../bin/sh: 1: qwerty: not found<br>$</pre>
</details>

<details>
<summary>Same error with your program hsh:</summary>
<pre>$ echo "qwerty" | ./hsh<br>./hsh: 1: qwerty: not found<br>$ echo "qwerty" | ./././hsh<br>./././hsh: 1: qwerty: not found<br>$</pre>
</details>

## Testing

<details>
<summary>The shell should work like this in interactive mode:</summary>
<pre>$ ./hsh<br>($) /bin/ls<br>hsh main.c shell.c<br>($)<br>($) exit<br>$</pre>
</details>

<details>
<summary>But also in non-interactive mode:</summary>
<pre>$ echo "/bin/ls" | ./hsh<br>hsh main.c shell.c test\_ls\_2<br>$<br>$ cat test\_ls\_2<br>/bin/ls<br>/bin/ls<br>$<br>$ cat test\_ls\_2 | ./hsh<br>hsh main.c shell.c test\_ls\_2<br>hsh main.c shell.c test\_ls\_2<br>$</pre>
</details>

## Authors

- [Charles Obimnaeto Egesionu](https://github.com/IamNaeto)

- [Jane Nginika](https://github.com/Nginika)

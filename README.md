** CODING MY - SIMPLE SHELL **


# Simple Shell Project

A simple shell implementation in C programming language.

## Introduction

This project provides a basic shell interface that allows users to interact with the operating system through commands and input/output operations. It supports basic functionalities like executing commands, handling input/output redirection, and piping between commands.

## Building and Running

To build the simple shell project, you will need to have the following prerequisites:

- A C compiler
- A POSIX-compliant operating system (e.g., Linux, macOS, Unix)

Once you have the prerequisites, follow these steps to build the project:

1. Clone or download the project repository.
2. Navigate to the project directory.
3. Run the following command to build the project:

gcc -Wall -Werror -Wextra -pedantic -std=gnu89 *.c -o hsh

## Testing
Your shell should work like this in interactive mode:

$ ./hsh
($) /bin/ls
hsh main.c shell.c
($)
($) exit
$

## Concepts
For this project, we expect you to look at these concepts:

Everything you need to know to start coding your own shell
Approaching a Project
All about Team Projects + Pairings + FAQ (A must read)
Struggling with the sandbox? Try this: Using Docker & WSL on your local host

## Resources
Read or watch:

Unix shell
Thompson shell
Ken Thompson
Everything you need to know to start coding your own shell concept page
man or help:

sh (Run sh as well)

# More Info
## Output
Unless specified otherwise, your program must have the exact same output as sh (/bin/sh) as well as the exact same error output.
The only difference is when you print an error, the name of the program must be equivalent to your argv[0] (See below)

# Tasks
## 0. Betty would be proud
mandatory

## 1. Simple shell 0.1
mandatory
Write a UNIX command line interpreter.

Usage: simple_shell
Your Shell should:

Display a prompt and wait for the user to type a command. A command line always ends with a new line.
The prompt is displayed again each time a command has been executed.
The command lines are simple, no semicolons, no pipes, no redirections or any other advanced features.
The command lines are made only of one word. No arguments will be passed to programs.
If an executable cannot be found, print an error message and display the prompt again.
Handle errors.
You have to handle the “end of file” condition (Ctrl+D)
You don’t have to:

use the PATH
implement built-ins
handle special characters : ", ', `, \, *, &, #
be able to move the cursor
handle commands with arguments
execve will be the core part of your Shell, don’t forget to pass the environ to it…

## 2. Simple shell 0.2
mandatory
Simple shell 0.1 +

Handle command lines with arguments

## 3. Simple shell 0.3
mandatory
Simple shell 0.2 +

Handle the PATH
fork must not be called if the command doesn’t exist

## 4. Simple shell 0.4
mandatory
Simple shell 0.3 +

Implement the exit built-in, that exits the shell
Usage: exit
You don’t have to handle any argument to the built-in exit

## 5. Simple shell 1.0
mandatory
Simple shell 0.4 +

Implement the env built-in, that prints the current environment

## 6. Simple shell 0.1.1
#advanced
Simple shell 0.1 +

Write your own getline function
Use a buffer to read many chars at once and call the least possible the read system call
You will need to use static variables
You are not allowed to use getline
You don’t have to:

be able to move the cursor

## 7. Simple shell 0.2.1
#advanced
Simple shell 0.2 +

You are not allowed to use strtok

## 8. Simple shell 0.4.1
#advanced
Simple shell 0.4 +

handle arguments for the built-in exit
Usage: exit status, where status is an integer used to exit the shell

## 9. setenv, unsetenv
#advanced
Simple shell 1.0 +

Implement the setenv and unsetenv builtin commands

setenv
Initialize a new environment variable, or modify an existing one
Command syntax: setenv VARIABLE VALUE
Should print something on stderr on failure
unsetenv
Remove an environment variable
Command syntax: unsetenv VARIABLE
Should print something on stderr on failure

## 10. cd
#advanced
Simple shell 1.0 +

Implement the builtin command cd:

Changes the current directory of the process.
Command syntax: cd [DIRECTORY]
If no argument is given to cd the command must be interpreted like cd $HOME
You have to handle the command cd -
You have to update the environment variable PWD when you change directory
man chdir, man getcwd

## 11. ;
#advanced
Simple shell 1.0 +

Handle the commands separator ;

## 12. && and ||
#advanced
Simple shell 1.0 +

Handle the && and || shell logical operators

## 13. alias
#advanced
Simple shell 1.0 +

Implement the alias builtin command
Usage: alias [name[='value'] ...]
alias: Prints a list of all aliases, one per line, in the form name='value'
alias name [name2 ...]: Prints the aliases name, name2, etc 1 per line, in the form name='value'
alias name='value' [...]: Defines an alias for each name whose value is given. If name is already an alias, replaces its value with value

## 14. Variables
#advanced
Simple shell 1.0 +

Handle variables replacement
Handle the $? variable
Handle the $$ variable

## 15. Comments
#advanced
Simple shell 1.0 +

Handle comments (#)

## 16. File as input
#advanced
Simple shell 1.0 +

Usage: simple_shell [filename]
Your shell can take a file as a command line argument
The file contains all the commands that your shell should run before exiting
The file should contain one command per line
In this mode, the shell should not print a prompt and should not read from stdin

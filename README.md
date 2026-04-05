# Minishell

<p align="center">
  <img src="https://img.shields.io/badge/language-C-blue">
  <img src="https://img.shields.io/badge/build-Makefile-success">
  <img src="https://img.shields.io/badge/norminette-passing-brightgreen">
  <img src="https://img.shields.io/badge/platform-linux-lightgrey">
  <img src="https://img.shields.io/badge/project-42-black">
</p>

<p align="center">
  <b>A simplified Bash-like shell written in C</b><br>
  Processes • Pipes • Redirections • Parsing • Signals
</p>

---

## Overview

Minishell is a simplified implementation of a Unix shell inspired by bash.

The objective of this project is to understand how shells work internally by implementing command parsing, process management, pipes, redirections, environment variables, and signal handling.

The program provides an interactive prompt where users can execute commands similarly to bash while learning how operating systems manage processes and file descriptors.

---

## Features

### Command Execution
- Execute programs using:
  - PATH environment variable
  - absolute paths
  - relative paths

### Built-in commands

| Command | Description |
|--------|-------------|
| echo -n | display text |
| cd | change directory |
| pwd | show current directory |
| export | create/update environment variables |
| unset | remove environment variables |
| env | display environment variables |
| exit | exit the shell |

### Pipes and Redirections

| Operator | Description |
|----------|-------------|
| \| | pipe output between commands |
| < | redirect input |
| > | redirect output |
| >> | append output |
| << | heredoc |

### Environment Variables
- $VAR expansion
- $? last command exit status

### Signal Handling

| Shortcut | Behavior |
|----------|----------|
| Ctrl-C | display new prompt |
| Ctrl-D | exit shell |
| Ctrl-\ | ignored |

### Parsing
- single quotes '
- double quotes "
- pipes and redirections
- environment variable expansion

---

## Example Usage

### basic commands

echo hello world

pwd

cd ..

ls -la


### pipes

ls | grep minishell


### redirection

echo hello > file.txt

cat file.txt


### heredoc

cat << EOF
hello
EOF


### environment variables

echo $PATH

echo $?

---

## Project Architecture

input → lexer → parser → expander → executor  
                                   │  
                                   ├── builtins  
                                   ├── pipes  
                                   ├── redirections  
                                   └── execve  

---


## Usage

Run minishell:

./minishell


Example commands:

echo hello

pwd

cd ..

echo "text" > file.txt

cat file.txt

cat file.txt | grep text

echo $PATH

echo $?


---

## Allowed Functions

readline  
fork  
execve  
wait  
waitpid  
pipe  
dup  
dup2  
open  
read  
write  
close  
signal  
sigaction  
getenv  
chdir  
getcwd  
perror  
strerror  
malloc  
free  

---

## Learning Outcomes

Understanding of:

- Unix process model
- file descriptors
- pipes and redirections
- signals
- parsing logic
- memory management
- Makefile workflow
- shell behavior

---

## Author

Houssam Er Rehyby

---

## Notes

Part of the 42 curriculum focused on low-level programming and operating system fundamentals.

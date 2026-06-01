# Linux Commands and System Navigation
This document contains Linux commands practiced while learning Ubuntu 24.04 and operating systems concepts.

## List Directories
### Command

```bash
ls /
```

Lists all directories and files located under the root (`/`) directory.

### Command

```bash
ls --help
```
Displays help information and available options for the `ls` command.

### Command

```bash
ls -l /
```
Displays files and directories in long list format, including:
* Permissions
* Owner
* Group
* File size
* Modification date
* 
### Command

```bash
ls -al /
```
Displays all files, including hidden files and directories.
Hidden files in Linux begin with a dot (`.`).
Example:
```text
.bashrc
.profile
```

## Print Working Directory
### Command

```bash
pwd
```
Displays the current directory path.

# File and Text Manipulation

## Display File Contents

### `cat` Command

```bash
cat important_doc.txt
```
Displays the contents of a file in the terminal.

## View Large Files

### `less` Command

```bash
less important_doc.txt
```
Displays file contents one screen at a time.

### Useful Navigation Keys

| Key                 | Function                  |
| ------------------- | ------------------------- |
| Up / Down           | Move line by line         |
| Page Up / Page Down | Move by page              |
| g                   | Jump to beginning of file |
| G                   | Jump to end of file       |
| /word               | Search for a word         |
| q                   | Quit less                 |


### `head, Command

```bash
head important_doc.txt
```
Displays the first 10 lines of a file.

### `tail` Command

```bash
tail important_doc.txt
```
Displays the last 10 lines of a file.

## Edit Files Using Nano

### Command

```bash
nano my_file.txt
```
Opens a file for editing using the Nano text editor.

### Useful Shortcuts

| Shortcut | Function  |
| -------- | --------- |
| Ctrl + G | Help menu |
| Ctrl + X | Exit Nano |
| Ctrl + O | Save file |


## Search Inside Files

### `grep` Command
`grep` is commonly used for:

* Log analysis
* Security investigations
* System administration
* Text searching

```bash
grep cow animal.txt
```
Searches for the word "cow" inside the file.

### Command

```bash
grep cow* animal.txt
```
Uses pattern matching to search for text beginning with "cow". asterisk wildcard command here >grep cow* _animal.txt and ​you can see that it found cow in all files name animal.

## Input Output and Pipeline
### Standard Input (stdin)
Standard Input (stdin) is where a command receives its input. By default, this is the keyboard.
Example
`cat` Anything typed into the terminal is passed to cat through stdin.
### Standard Output (stdout)
Standard Output (stdout) is where a command sends its normal output. By default, this is the terminal screen.
Example
```bash
echo "Hello Linux"
```
Output:
```bash
Hello Linux
```
### `>` Output Redirection
We echo the text woof here ​but instead of sending it to our screen by default, ​we're going to redirect the output to a file ​using the standard out redirector operator. 
this operator will create this sile and overwrite the content of the file.

### `>>` Append Redirection 
This is append operator if you donot want the to overwrite the content of the file this operator will simply add the given text into the given file.

### `<` Input Redirection
The `<` operator redirects a file to a command's standard input.
```bash
cat < dog.txt
```
Output:
```bas
woof
belt
```

Both commands below display the contents of a file:
``` bash
cat dog.txt
cat < dog.txt
```
The difference is that in the first command cat opens the file itself, while in the second command the shell redirects the file contents to cat through stdin.​

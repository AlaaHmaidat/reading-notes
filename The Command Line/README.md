# The Command Line
The best way to learn the Linux command line is as a series of small, easy to manage steps.

## So what are they exactly?
A command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.

## The Shell
 If you would like to know which shell you are using you may use a command called echo to display a system variable stating your current shell. echo is a command which is used to display messages.

```javascript
echo $SHELL

```
## So where are we?
Print Working Directory - ie. Where are we currently.
```javascript
pwd
```
## What's in Our Current Location?
List the contents of a directory.

```javascript
ls
```
```javascript
ls -l
```

## Let's Move Around a Bit
Change Directories - ie. move to another directory.

```javascript
cd [location]
```
## Linux is an Extensionless System
obtain information about what type of file a file or directory is.

```javascript
file [path]
```
### Notes
1- Everything is a file under Linux Even directories.

2- Linux is an extensionless system
Files can have any extension they like or none at all.

3- Linux is case sensitive

4- Beware of silly typos.

## Quotes
 Anything inside quotes is considered a single item.


```javascript
cd 'Holiday Photos'
```
## Escape Characters
Another method is to use what is called an escape character, which is a backslash ( \ ). What the backslash does is escape (or nullify) the special meaning of the next character.

```javascript
cd Holiday\ Photos
```
## Hidden Files and Directories
List the contents of a directory, including hidden files.

## Exit
To exit the man pages press 'q' for quit.

```javascript
q
```
## So what are they exactly?
Look up the manual page for a particular command.

```javascript
man <command>
```

## Searching
Do a keyword search for all manual pages containing the given search term.

```javascript
man -k <search term>
```
### Notes
The man pages are your friend.
Instead of trying to remember everything, instead remember you can easily look stuff up in the man pages

## Making a Directory
Make Directory - ie. Create a directory.
```javascript
mkdir
```
## Removing a Directory
Remove Directory - ie. Delete a directory.
```javascript
rmdir
```
## Creating a Blank File
```javascript
touch
```
## Copying a File or Directory

```javascript
cp
```
## Moving a File or Directory
Move - ie. Move a file or directory (can also be used to rename).

```javascript
mv
```
## Removing a File (and non empty Directories)

```javascript
rm
```
### Notes 
No undo

The Linux command line does not have an undo feature. Perform destructive actions carefully.

Command line options

Most commands have many useful command line options. Make sure you skim the man page for new commands so you are familiar with what they can do and what is available.


### An "ah-hah" moment for me was learning about hidden files in Linux. I found it interesting that any file or directory whose name begins with a dot (.) is considered hidden, and this is a simple and elegant mechanism for protecting critical configuration files from accidental modification or deletion. It was also interesting to learn that the "ls" command doesn't show hidden files by default, and you need to use the "-a" option to view them.

## Things I want to know more about
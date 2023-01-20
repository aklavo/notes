# Linux Terminal Notes
## 1.0 Basic Definitions  
**Command** : An instruction typed in the terminal and submitted to the shell for interpretation.  
**Shell** : A program that interprets commands for meaning.  
**Terminal** : A graphical window where commands can be typed and submitted to the shell.    

## 2.0 Command Structure
```
commandName -options arugments
```
### 2.1 Command names
`commandName` must be a valid program on the Shell’s Path. To check this, use the which command like so:  
```
which commandName 
```
If a path is returned, then the commandName is valid and vice versa.

### 2.2 Options
You can specify options for each command to customise the commands behaviour. These canbe either “short-form” options or “long-form” options.  

Short-form:  
```
commandName –abc args
```

Long-form:  
```
commandName --alpha --beta --charlie args
```

### 2.3 Command Line Aurgments
Command line arguments are a type of input that commands operate on.
Some commands can take an unlimited amount of inputs (seperatede by spaces), some take a specific amount, and some take none at all. 
```
commandName -ab arg1 arg2
```
or...  
```
commandName -a arg1 -b arg2 arg3
```


## 3.0 Shortcuts
Open terminal = `CRTL + ATL + T`  
Close terminal = `CRTL + D`  
Break out of command/process = `CRTL + C`  
Clear terminal = `CTRL + L`  
Move cursor to beginning = ` CRTL + A`  
Move cursor to end = ` CRTL + E`  
Clear line= ` CRTL + U`  
Clear last word = `CRTL + W`  
Search command history = `CRTL + R`

## 4.0 Basic Commands
| Command | Description |
|--------|-------------|
| `echo` | Prints command line arugumen to standard output (SO).|
| `cat` | Stick files together and write joined file to SO. Good for viewing the contents of.|
 `history` | Show commands previously entered.|
|`man -k <search term>`|Search the manual for pages matching \<search term>.|

## 5.0 Command Input and Output
![Command-IO](/static/command-IO.png "Command Input and Output")  
Standard Data Streams can be **redirected** and are identified using their stream number. Redirection of the standard output of one command to the standard input of another command is known as **piping**.  

### 5.1 Redirecting Standard Output:
Standard output is stream number 1. 
```
commandName –options arguments > destination
```
### 5.2 Redirecting Standard Error:
Standard error is stream number 2.
```
commandName –options arguments 2> destination
```
Standard error can be redirected at the same time as standard output:
```
commandName –options arguments 1> output_destination 2> error_destination
```
### 5.3 Redirecting Standard Input:
Standard Input is stream number 0. 
```
commandName –options arguments < input_source
```
### 5.4 Piping:  
Piping is the connection of the standard output of one command to the standard input of
another command. Piping using the pipe character (|) which is accessed by pressing
SHIFT + BACKSLASH (\\) on most keyboards.
```
commandOne –options arguments | commandTwo –options arguments
```
### 5.5 Taking “Snapshots” of pipeline data using the tee command: 
The tee command allows us to take a “snapshot” of the data in the pipeline without breaking the pipeline.
```
commandOne –options arguments | tee snapshot.txt | commandTwo –options arguments
```
Here, a snapshot of the data coming out of commandOne is saved in snapshot.txt, but the data is also successfully piped through to commandTwo.

### 6.0 Aliases  
Aliases allow you to save your pipelines and commands with easy to remember nicknames so that they can be used later much easier. 
Here is how you define an alias in .bashrc (or .zshrc etc.):

```
alias aliasName=”THING YOU WANT TO ALIAS”
```
Generic Command Structure: 
commandName options inputs (--longformOption, -shortFormOption)
    - commandName needs to be on the shell's search path. else add it 

## Using the Linux Manual Pages 
Manual Structure: The manual has codes for each kind of commands: 
1. User Commands 
2. System Calls 
3. C Library Functions 
4. Devices and Special Files 
5. File Formats and Conventions 
6. Games 
7. Miscellaneous 
8. System Administration 
(types 1, 5, 8 used most often)

```
man -k which
```
(k matches for regex patterns and lists commands containing 'which') 
... means the quantity can be appended at the end 
[] means a quantity is optional 
<> means it is mandatory  
[-a | -f] this format means one or the other 

## Command Input + Output 
Commands are connected using pipelines. We can redirect the standard output of one command to the standard input of another in a process known as piping. 
Command Inputs : Standard Input and Command Arguments
Command Outputs: Standard Output and Standard Error

Note:
-  Data streams can be piped together. Arguments cannot be. 
- Data Streams have numbers associated with them. 0 is standard input, 1 is standard output, 2 is standard error. 

Redirecting Standard Input: cat 0< input.txt 1> hello.txt

Redirecting Standard Output: cat 1> output.txt would overwrite. cat 1>> output.txt would append. 

Redirecting Standard Error: cat 2>> error.txt 

## Piping 
Uses the output of one command into the input of another command. 
```
date 1> date.txt
cut 0< date.txt --delimiter " " --fields 1
```
Here we use input of cut from date.txt file. 
```
date | cut --delimiter " " --fields 1
```
Here we pipe the output of date directly into cut. 

### Piping to more than one places:
Conventionally data can be streamed to only one place. For eg, in the above example, if we want to store the date in a file and then use that as input for the cut command, that will not work, as the output from date is streamed into date.txt. 
Example of what will NOT work: 
```
date 1> date.txt | cut --delimiter " " --fields 1
```
### tee Command: 
This command enables 2 way show, just like the shape T. The horizontal flow is uninterrupted, and a vertical flow is added to the tee command argument. 
Example: 
```
date | tee date.txt | cut --delimiter " " --fields 1
```
Now output of date is stored in date.txt. Also the horizontal data flow remains uninterrupted. 

### xargs Command: 
Piping redirects the output of commands(STDOUT) to be the input(STDIN) of some other commands. However, some commands accept only command line arguments. This is where 'xargs' comes in.  
Example: 
```
date | echo
```
Doesnt work cause echo accepts only command line args. Use this : 
```
date | xargs echo 
```
We can also pass xargs and CLA together. However echo will process the CLA first. Same with 'rm' command. Let file 'filesToDelete.txt' contain 'fileA.txt' and 'fileB.txt'. 
```
cat filesToDelete.txt | rm
```
 does not work. Instead : 
 ```
 cat filesToDelete.txt | xargs rm 
 ```

Misc: 
- cal - Calendar for the current month
- ^L - clear
- !4 - will run the 4th command (having line number 4) from history
- exit - close terminal
- which - locates the folder where command is present 
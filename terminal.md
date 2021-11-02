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

Misc: 
cal - Calendar for the current month
^L - clear
!4 - will run the 4th command (having line number 4) from history
exit - close terminal
which - locates the folder where command is present 
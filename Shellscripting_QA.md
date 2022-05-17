# What is a shell ?
shell is a command line user interface for the linux OS.

# What is a shell script ?
its a text file containing one or more commands.

# How to pass the parameters to the script and how can I get those parameters?
Scriptname.sh parameter1 parameter2 
use $* to get the parameters.

# What are the different types of variables ?
system variables and user defined variables.

# List all the variables
`set` # will list all the variables system and user.

# write a script to add two numbers
```sh
echo “Enter no 1”read a 
echo “Enter no 2” read b 
c= ‘expr $a + $b’ 
echo “ $a+ $b=$c”
```

# What is the difference between break and continue commands ?
## Break
exit out of the loop, i.e for, while or until

## Continue
skip the current iteration and continue with the next iteration in the loop.

# what is the significance of the shebang line
    `#!/bin/sh`
    
This sequence of characters (`#!`) is called **shebang** and is used to tell the operating system which interpreter to use to parse the rest of the file.

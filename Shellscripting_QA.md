# How to pass the parameters to the script and how can I get those parameters?
Scriptname.sh parameter1 parameter2 
use $* to get the parameters.

# write a script to add two numbers
```sh
echo “Enter no 1”read a 
echo “Enter no 2” read b 
c= ‘expr $a + $b’ 
echo “ $a+ $b=$c”
```

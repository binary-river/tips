#Bash Tips

### source
`source [scriptname]`<br>
 : Allow using functions in file [scriptname] on command line 
<br><br>

### make
`make [target]`<br>
 : Run codes which is belong to target in makefile,
makefile is consisted like this
``` 
[target] : [dependencies..]
	[commands]
```
if you write dependencies, then command will only run when dependencies change.
<br><br>

### expr
`expr 1 + 2`<br>
 : Evaluate input, note that you should give space between numbers and arithmetic operators.
if you want to calculate fractions or numbers with decimals, then use bc
<br><br>

### bc
`bc [filename]`, `echo "expression" | bc -l`<br>
 : Evaluate math expression. you can calculate numbers with decimals, fracntion using this
<br><br>

### variable
`var_1="this is variable"`, `var_2=10`<br>
 : assigning data by using equal sign, there's no data type like other low level languages.<br>
Spaces are not allowed on either side of the equal sign when assigning data to variable.<br>
`echo ${var_1}`<br>
 : You can use variable which you assigned already using `${variable_name}`<br>
`var_1=$(ls -l | wc -l)`<br>
 : You can also assign result of shell command to a variable using `$(shell command)`.
Notice that linefeed does not be stored in a variable even when you assign variable using `ls -l` command<br>
`$@`, `$1 $2 $3...`, `$#`<br>
 : In a script, shell gives variables which allows you to use arguements, arguments info.<br>
- $@ means all arguments. you will get all arguments separated by spaces.<br>
- $1 $2 $3... mean a first argument, a second argument, a third argument. number means order of arguments<br>
- $# means number of arguments.

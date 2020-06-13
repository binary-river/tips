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

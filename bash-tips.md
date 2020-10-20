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
<br><br>

### Conditional Expression
`true || echo "after true"`<br>
`false || echo "after false"`<br>
 : Conditional Expression is compacted version of `if..else`. if first condition is true followed by ||, then next condition doesn't get a chance to be runned
 because first condition is true followed by || means whatever the next conditional expression gives, anyway total result will be true. So, in that way, 
the second conditional expression will not be runned. `false || echo "after false"` works just opposite of `true || echo "after true"`
<br><br>

### Array
`food=(chicken pizza hamburger cheese)`<br>
`echo ${food[1]}`, `echo ${food[2]}`, `echo ${food[*]}`<br>
 : You can declare array variable using () and each elements separated by space.<br>
Like other languages, index starts from zero, you can get elements by their index. And star(*) allows you to get all elements the array has separated by space 
<br><br>

### curl
`curl http://httpbin.org/get`, `curl http://website.org/textfile.txt`<br>
 : Curl is a tool for connection to other server. It will print the result you get from other server to standard output if you don't give -O option. You can download it as a file form using -O option. Note that you can't name files you want to download. Curl only download files from server as same name. Curl will replace files which have same name in your working directory to files you want to download.

### nmcli
`nmcli dev wifi list`, `nmcli dev wifi con [wifi-name] [wifi-pass]`
 : Connect wifi on terminal

### :
` while :; do echo "helloworld!"; sleep 10; done `, `if [ 1 = 1 ]; then :; else echo "helloworld!"`
 : Colon in shell is equivalent of a NOP(no operation). Its exit status is 0 when you command it.<br>
<br>Colon also can be used in conditinal statement like below
```
if [[ $var1 -eq 12 ]] 
 then :  # Do nothing when condition is true 
 else 
  echo "false!"
 fi
```
`: ${HOSTNAME?} ${USER?} ${MAIL?}`
 : Print error messages if one or more of variables given not set

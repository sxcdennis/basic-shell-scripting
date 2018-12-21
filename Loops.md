# Loops

In this section we'll go over loops which consist of **for, while, until** and **do**. Loops are exactly what they sound like- repeating tasks x amount of times.

By now you should be able to understand how to execute scripts and do all scripting standards. I will not be including them from this point forward. If you still need help with that, I suggest you go back and read and practice them.

# Video


## do and done

*do* and *done* are exactly how they sound. *do* a set of commands then *done* ends the commands.

**Syntax:**

```
do
  command(s)
done

```


## for loops

The *for loop* will take each item in a *list* , assign that item as the value of the variable, execute the *commands* between *do* and *done* then go back to the top, grab the next item in the list and repeat over.

A *list*
If do is in the same line as for, there needs to be a semicolon(**:**) after the

*list*  is a series strings, separated by spaces

You can set a number or letter *range* by using **{}** followed by two periods **..** example: ```{1..4}```

**syntax**

```

for variable in <list>
do
<commands>
done

```  

**Example 1:**

```

#!/bin/bash
#This script will be an example of for loops
# The file name will be called forloops.shell

for name in Joe John James
do
  echo Name: $names
done

```

**Output:**


```
Name: Joe
Name: John
Name: James

```

**Example 2**

```
#!/bin/bash
#This script will be an example of for loops using ranges
# The file name will be called forloops2.shell

for values in {1..10}
do
echo $values
done

```
**Output**

```

1
2
3
4
5
6
7
8
9
10

```

## while loops

*while* an expression is true, keep executing lines of code.

**syntax**

```
while [ <conditions here> ]
do
<commands>
done

```  

**Example 1:**

```

#!/bin/bash
#This script will be an example of while loops using ranges
# The file name will be called whileloops.shell

number=15
while [ $number -ge 10 ]
do
    echo $number
    ((number--))
done


```

**Output:**


```

15
14
13
12
11
10

```
Breakdown- *while* **number** ```15``` is true, *number* greater than or equal to 10 will *do* the following command. ```echo number ((number --))``` so using the double subtract we will decrease each *number* by 1 until it reaches 10.

**Example 2**

```

#!/bin/bash
#This script will be an example of while loops using until condition is met
# The file name will be called whileloops2.shell

while [ "$a" != "exit" ]
do
echo "Please type something or type exit to quit"
read a
echo "You typed $a."

```

This will indefinitely loop until you type exit .



# until loops

Until loops are similar to while loops. The difference is, it will execute commands until the conditions are met.

**syntax**

```

until [ <conditions here> ]
do
<commands>
done

```

**Example:**

```

#!/bin/bash
# Basic until loop
# Name will be until.bash
a=quit
until [ "$b" = "$a" ]
do
echo "Input something (Type $a to exit )"
read b
echo "You typed $b"
echo
done

```


**Output:**


```

Input something (Type quit to exit)
Hello
You typed Hello

Input something (Type quit to exit)
quit
You Typed quit

```

This script will keep looping until you type ```quit```



[< Back: Variables](https://sxcdennis.github.io/basic-shell-scripting/Variables "Variables") || [Next: If then Statements >](https://sxcdennis.github.io/basic-shell-scripting/If%20then%20Statements "If then Statements")

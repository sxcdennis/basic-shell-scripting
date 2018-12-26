# If Statements

**if** a particular test is true, then perform a  given set of actions. If isn't true, then don't perform those actions.
In this section we'll cover **if then**, **if else**, **if elif else**, and **boolean operators**


# Video:

https://youtu.be/TdP0HxtTXdU

## if then

**if** a particular test is true, then perform a given set of actions. If it isn't true then don't perform those actions.
Ending operations with fi- the opposite of if.

**Syntax**

```
if [ tests ]
then
 commands
fi

```
**Example**

```

#!/bin/bash
# Basic if then statements
# This will be named ifthen1.shell

echo "Type a number 1-10"
read num
if [ $num -gt 10 ]
then
  echo "That number is too big!"
  fi

if [ $num -le 10 ]
then
    echo "Thanks for choosing a number 1-10!"
fi

```

**Output 1**

```

Type a number 1-10
1
Thanks for choosing  a number 1-10!

```

**Output 2**

```

Type a number 1-10
11
That number is too big!

```

Notice the difference in outputs. How I had to create 2 **if** statements to make it work like this.


## if else

if then else statements are similar to if statements, but instead of using another if statement you can use just **else**


**Syntax**

```

if [ tests ]
then
  commands
else
  other commands
fi

```

**Example**

```
#!/bin/bash
# Basic if then else statements
# This will be named ifthenelse.shell

  echo "Type a number 1-10"
  read num
  if [ $num -gt 10 ]
then
  echo "That number is too big!"
else
  [ $num -le 10 ]
  echo "Thanks for choosing a number 1-10!"
fi

```

**Output 1**

```

Type a number 1-10
7
Thanks for choosing  a number 1-10!

```

**Output 2**

```

Type a number 1-10
20
That number is too big!

```

Notice how we get the same results as if then statements, but with less typing involved!


## if elif else
Sometimes you have several conditions that have to be met and may lead to different paths. That's where **elif** comes in.

**Syntax**

```

if [ tests ]
then
  < commands >
elif [ other tests ]
then
  < differnt commands >
else
    < other commands >
fi

```

**Example**

```
#!/bin/bash
# elif examples
# name of file will be elif.sh

  echo "Choose a number 1 or 2"
  read n
  if [ "$n" = "1" ]
then
  echo "You chose the number 1!"
elif [ "$n" = "2" ]
then
echo "You chose the number 2!"
else
[ "$n" = "*" ]
echo "You chose a value other than 1 or 2"
fi

```
**Output 1**

```
Choose a number 1 or 2
1
You chose the number 1!

```
**Output 2**

```
Choose a number 1 or 2
2
You chose the number 2!

```

**Output 3**

```
Choose a number 1 or 2
ABC
You chose a value other than 1 or 2

```

# boolean operators
**AND:** *-a* , *&&*
**OR:** *||* , *-o*
**Logical NEGATION** -  *!* (inverts conditions)


## AND: -a or &&
True if both left and right hand expression are true
Using **&&** requires double brackets

**Syntax**

```

[ test -a tests ]

Using &&:

[[ tests && tests]]
```

**Example**

```
#!/bin/bash
#And -a or &&
# call this and.sh

echo "Choose a number between 10-50"
read a
if [ $a -lt 51 -a $a -gt 9 ]
then
  echo " Your number is $a"
  else
  echo "You a chose value that is not 10-50. You chose $a ."
fi


```

**Output 1**

```

Choose a number between 10-50
49
Your number is 49

```
**Output 2**
```

Choose a number between 10-50
55
You chose a value that is not 10-50. You chose 55.

```
You can try using **&&** but remember to use double brackets **[[]]**


## OR -o and ||

True if left or right hand expression is true.  Using ```||``` requires using double brackets **[[]]**


**Syntax**

```

[ test -o tests ]

Using ||:

[[ tests || tests]]

```

**Example**

```

#!/bin/bash
#OR using -o and ||
# call this or.sh

echo "Enter a number less than 15 or greater than 50"
read a
if [ $a -lt 15 -o $a -gt 50 ]
then
echo "You chose a number less than 15 or greater than 50"
else
echo "You chose a value not less than 15 or greater than 50"
fi

echo
echo "Enter a number less than 25 or greater than 40"
read a
if [[ $a -lt 25 || $a -gt 40 ]]
then
echo "You chose a number less than 25 or greater than 40"
else
echo "You chose a value not less than 25 or greater than 40"
fi


```

**Output**

```
Enter a number less than 15 or greater than 50
5
You chose a number less than 15 or greater than 50

Enter a number less than 25 or greater than 40
25
You chose a number not less than 25 or greater than 40.

```

## Logical Negation  !

Logical negation *!* negates statements turning true statements to false and vise versa.

**Syntax**

```

[ test1 ! test2 ]

or
if [ ! test ]
then command
fi
```

**Example 1**

```

#!/bin/bash
# Using logical negation example
# name this logneg1.sh
# Example of [ test1 | test 2]

echo
echo "I am thinking of number 1-10. What do you think it is?"
read a
if [ $a != 8 ]
then
  echo "You chose $a . That is not my number!"
else
    echo "Correct that is my number!"
fi

```

**Output 1**

```

I am thinking of a number 1-0. What do you think it is?
1
You chose 1 .  That is not my number!


```
**Output 2**

```

I am thinking of a number 1-0. What do you think it is?
8
Correct that is my number!

```
**Example 2**

```
#!/bin/bash
# Using logical negation example
# name this logneg2.sh
# Example of [ ! test]

if [ ! -f /home/scripts/myfile.txt ] ; then
echo "File NOT FOUND!!"
else
echo "File found!!"
fi

```

**Output**

```

File NOT FOUND!!

```
Lets say you made the file by using ```touch /home/scripts/myfile.txt```

Then your output would be ```File found!!```


[< Back: Loops](https://sxcdennis.github.io/basic-shell-scripting/Loops "Loops") || [Next: Case Statements >](https://sxcdennis.github.io/basic-shell-scripting/Case%20Statements "Case Statements")

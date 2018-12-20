# Variables
In this section we'll talk about variables - how to define them, Input/Output variables, Special Variables and Parameter Expansions.
A variable is memory to where we can assign value, and manipulate its contents.
As we progress through this section, some standard formatting is not input into the scripts, but you should be getting used to doing it on your own.
Also in the command line outputs, I do not mention using ```chmod``` so please take note of that.  
# Videos

# Define Variables

To define variables in simple terms is **VARIABLE=Value**. (Note: There are no spaces between the **=** sign) <br>
To display the variables they are output by the **$** sign followed by variable. <br>

Example Script:
```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This is a script that defines simple variables
# Date Modified: 12/13/2018

p=pwd
d=date
l=ll
wo=whoami
num=200

echo Run variables
echo
echo $p
echo $d
echo $l
echo $wo
echo $num
echo
expr $num + 1
$p
$d
$l
$wo
echo
echo End of Script
```

As you can see for each output is a bit different. We first start by defining all the variables:

```
p=pwd
d=date
l=ll
wo=whoami
num=200
```
Then run each one using **echo** and as you can see it just displays each **value**  <br>
Next we follow up by using the application **expr** which prints  value of expression to standard output. As you can see we add it by 1.<br>
Next we see each **Variable** alone<br>
```
$p
$d
$l
$wo
```
As you can see it just uses each of the **values** of each **variable** as commands. <br><br>


# Input and Output (Interactive Scripts)
There are some scripts that can be interactive by using the **read** command. <br>
The following script displays a name, then asks for your name then displays your name. <br>

```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: Use of read
# Date Modified: 12/13/2018

echo Hello, my name is Robot
echo
echo What is your name?
read yourname
echo "Hello $yourname - What a wonderful name!"
echo End of Script
```

Lets say you want to make a script that creates a file name with your input but with the extension of **.file** The following is an example of that: <br>
```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: Create file with input and extension of .file
# Date Modified: 12/13/2018

echo "What would you like to name your file?"
read NAME1
echo "I will create a file named ${NAME1}.file"
touch "${NAME1}.file"
echo End of Script

```
Notice how the variable for the previous example is closed by curly braces **{}**<br>
If you were to use it without the curly braces, it would just think that you're variable is ```$NAME1.file``` instead of ```$NAME1``` <br>
Also notice that there are double quotes **""** between commands. This is because without the quotes the arguments for the command would run differently.<br>
For example lets say you run the command ```#touch my file.file``` you would create **two** files: my and file.file vs ```#touch "my file.file"``` which would create **one** file: my file.file

# Special Variables
There are a set of variables that are already set for you already. They cannot have values assigned to them. The following is a table with all of the special variables. I urge you to practice them on your own.
<table>
  <thead>
    <tr>
      <th>Variable</th>
      <th>Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>$0 </td>
      <td>This will produce the pathname along with the filename. </td>
      <tr>
      <td>$n</td>
      <td>Shell allows only nine parameters to be referenced n = 1–9 but Bash allows n to be greater than 9 if specified with curly braces: ${n} </td>
      </tr>
      <tr>
      <td> $# </td>
      <td> Number of command-line parameters stated.</td>
      </tr>
      <tr>
      <td> $@ </td>
      <td>All parameters stated on command line ("$1" "$2" "$3" "$4" etc…)</td>
      </tr>
      <tr>
      <td> $IFS</td>
      <td> **Internal Field Separator:** The default value is **SPACE**, **TAB** and a **NEWLINE**. You can change this to whatever you want. </td>
      </tr>
      <tr>
      <td>$* </td>
      <td> All parameters stated on command ("$1" "$2" "$3" "$4" etc…). The values are separated by the first character in $IFS. Does not preserve quoting and whitespaces.</td>
      </tr>
      <tr>
      <td> $$</td>
      <td> Displays process number of current running shell.</td>
      </tr>
      <tr>
      <td> $!</td>
      <td>Number of last background process.</td>
      </tr>
      <tr>
      <td>$?</td>
      <td>Exit value of last executed command.</td>
      </tr>
    </tr>
  </tbody>
</table>
<br>


## $0
Will produce the pathname along with the filename.

**Example:** Your script name is **test1.sh** located in ```/home/scripts```
If you call the variable it would output ```/home/scripts/test1.sh```


##$n or $1-$9 or ${n}

These are whatever **named** parameters to which the script was called with.
For example lets say I have a script named testpara1.sh :
```
#!/bin/bash
# filename is testpara1.bash
echo "My First parameter is $1"
echo "My Second parameter is $2"
```
Now if you call the script without stating the parameters it would

**Output:**

```
My First parameter is
My Second parameter is
```
Now try running the script with parameters. For example: ```./testpara1.bash Onepara TwoPara```

**Output:**

```
My First parameter is Onepara
My Second parameter is TwoPara
```

Shell allows you to only go from 1-9 but you can go above 9 by using **{}** in bash.

**For example:**

**Input script:**
```
#!/bin/bash
# filename is testpara10.bash
echo "This will be the 10th parameter ${10}"
```

**Command Line:**

```
#./testpara10.bash 1 2 3 4 5 6 7 8 9 ten

```
**Output:**
```
This will be the 10th parameter ten

```


## $#
Displays the number of parameters.

**For example:**

**Input Script:**
```
#!/bin/bash
# This will display number of parameters
# Filename is testpara3.bash
echo "My first parameter is $1"
echo "My second parameter $2"
echo "How many parameters total: $#"
```

**Command Line:**

```
#./testpara3.bash para1 para2

```

**Output:**
```
My first parameter is para1
My second parameter is para2
How many parameters total: 2
```


## $@
Displays all parameters stated on the command line.

**Example:**

**Input Script:**
```
#!/bin/bash
# This will display  all parameters.
# Filename is displayall.bash
echo "My first parameter is $1"
echo "My second parameter is $2"
echo "How many parameters total: $#"
echo "All of the parameters are: $@"
```
**Command Line:**

```
#./displayall.bash para1 para2

```

**Output:**
```
My first parameter is para1
My second parameter is para2
How many parameters total: 2
All of the parameters are: para1 para2
```

## $IFS
Abbreviation for Internal Field Separator. The default value of it is either SPACE(spacebar), TAB and a New Line. You have the option to change this in a script as well.

**Example 1:**

**Input Script:**
```
#!/bin/bash
# This will be an example of $IFS changed
# Filename is IFS1.bash
IFS="-"
echo "Please input values separated by hyphens"
read a b c
echo "a is $a b is $b c is $c"
```
**Command Line:**

```
#./IFS1.bash

```

**Output:**
```
Please input values separated by hyphens
aa-bb-cc
a is aa b is bb c is cc
```
Now if you wanted to run the script using either TAB or Space it would have a different output

**Output:**
```
Please input values separated by hyphens
aa bb cc
a is aa bb cc b is c is
```

Now lets see an example of using the default IFS and the newly one created.

**Example2:**
```
#!/bin/bash
# This will be an example of $IFS changed and the default $IFS
# Filename is IFS2.bash

default_IFS="$IFS"
IFS="-"

echo "Please input values separated by hyphens"
read a b c
echo "Please input some values for using default IFS"
read x y z

IFS=$default_IFS

echo "New IFS: a is $a b is $b c is $c"
echo "Default IFS: x is $x y is $y z is $z"

```

**Command Line:**

```
#./IFS2.bash

```

**Output:**
```
Please input values separated by hyphens
aa-bb-cc
Please input some values for using default IFS
AA BB CC

New IFS: a is aa b is bb c is cc
Default IFS: x is AA y is BB z is CC

```
You can play around with the above example to see how it works.
Now lets say you want to use both the NEW IFS & Default IFS.
You would just move the line ```IFS=$default_IFS``` to where all the top variables are listed.

**Example3:**
```
#!/bin/bash
# This will be an example of using both default $IFS and NEW IFS
# Filename is IFS3.bash

default_IFS="$IFS"
IFS=$default_IFS
IFS="-"
echo "Please input values for COMBINED IFS separated by hyphens or spaces or TABS"
read a b c
echo "Please input values for COMBINED IFS separated by hyphens or spaces or TABS"
read x y z
echo "Combined IFS First Values: a is $a b is $b c is $c"
echo "Combined IFS Second Values: x is $x y is $y z is $z"
```

**Command Line:**

```
#./IFS3.bash

```

**Output:**

```
Please input values for COMBINED IFS separated by hyphens or spaces or TABS
aa-BB cc
Please input values for COMBINED IFS separated by hyphens or spaces or TABS
AA bb-CC

Combined IFS First Values: a is AA b is BB c is cc
Combined IFS Second Values: x is AA y is bb z is CC
```

## $*

Similar to **$@** - Displays all parameters stated on command line. The values are separated by the first character in $IFS. Does not preserve quoting and whitespaces.

**Example:**

This cannot be displayed without the use of functions or if then statements. Which is discussed later in the guide.
For now, just look at this script or come back to it.

**Input Script:**

```
#!/bin/bash
# This will display the difference between $@ and $*.
# Filename is displaydiff.bash
with_at()
{
  printf "%s\n" "$@"  
}
with_star()
{
  printf "%s\n" "$*"  
}
echo "This is with @:"
with_at "one" "two three" "four"
echo
echo "This is with *:"
with_star "one" "two three" "four"
```

**Command Line:**

```
#./displaydiff.bash
```


**Output:**

```
This is with @:
one
two three
four

This is with *:
one two three four
```

## $$
Displays process number of current running shell.

**Example:**

**Input Script:**

```
#!/bin/bash
# This will be an example of using $$
# Filename is displaypronum.bash

echo "This is the process ID number of the script on the current running shell: $$"
ps -A | grep $$

```

**Command Line:**
```
./displaypronum.bash

```

**Example Output:**

```

This is the process ID number of the script on the current running shell: 123029
123029 tty1     00:00:00 displaypronum.b

```

Notice how using ```ps -A | grep $$``` displays the the ID line.

## $!
Number of last background process.

**Example:**

**Input Script:**

```
#!/bin/bash
# This will be an example of using $!
# The file name will be: lastbg.bash

sleep 100&
echo "This is the last background process ID: $!"
ps -A | grep $!
```

**Command Line:**

```
./lastbg.bash

```

**Example Output:**

```
This is the last background process ID: 123550
123550 tty1   00:00:00 sleep
```

## $?

Exit value of last executed command.

Typically for the program to pass the **0** value stands for successful executions and **1 or higher** for failed executions

**Example:**

**Input Script:**

```
#!/bin/bash
# This is an example of using $? which will display values of successful executions vs failed
# The file name will be called: values.bash


cat nothere.txt
echo The value of the first command is: $?

touch nothere.txt
echo The value of the second command is: $?

rm nothere.txt
echo The value of the third command is: $?

```

**Command Line:**

```
./values.bash

```


**Output:**

```
The value of the first command is: 1
The value of the second command is: 0
The value of the third command is: 0

```
As stated earlier, the values **0** means successful execution while **1 or higher** is failed executions.
Looking back at the script, the first command ```cat nothere.txt``` did not exist at the moment so the command had failed.
We then follow up by using ```touch nothere.txt``` which is successful. Then finally followed by ```rm nothere.txt``` which removes the file created and is a successful command.


# Parameter Expansions
Parameter Expansions are similar to special variables. Here we'll talk about **:- , :=, :?, and :+**

The following a table with parameter expansions:

<table>
  <thead>
    <tr>
      <th>Parameter Expansions</th>
      <th>Function</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td> ${*parameter* **:-** *word*} </td>
      <td>If *parameter* is unset or null, then whatever you put as *word* substitutes *parameter* . Otherwise, the *value* [ what you typed] of *parameter* is substituted by whatever you typed in. </td>
      <tr>
      <td>${*parameter* **:=** word}</td>
      <td> If parameter is unset or null, the expansion of word is assigned to parameter. The value of parameter is then substituted. Positional parameters and special parameters may not be assigned to in this way. </td>
      </tr>
      <tr>
      <td> ${*parameter* **:?** word}</td>
      <td> If *parameter* is null or unset, the expansion of word (or a message to that effect if word is not present) is written to the standard error and the shell, if it is not interactive, exits. Otherwise, the value of parameter is substituted.</td>
      </tr>
      <tr>
      <td> ${*parameter* **:+** word} </td>
      <td> If *parameter* is null or unset, nothing is substituted, otherwise the expansion of word is substituted.</td>
      </tr>
    </tr>
  </tbody>
</table>
<br>

## :-
If *parameter* is unset or null, then whatever you put as *word* substitutes *parameter* . Otherwise, the *value* [ what you typed] of *parameter* is substituted by whatever you typed in.

**Example:**

**Input Script:**

```
#!/bin/bash
# This will be an example of #-
# We will name this file paraexpan1.bash
echo "Is your name `whoami` ? Enter your name."
read yourname
echo "Your name is: ${yourname:-Friend}"

```

**Command Line:**

```
./paraexpan1.bash

```

**Output 1:**

```
Is your name root ? Enter your name.

Your name is Friend  
```

**Output 2:**

```
Is your name root ? Enter your name.
Dennis
Your name is Dennis   
```
As you can see the difference in the outputs. We look back at the definition of this.
If *parameter* ```$yourname``` is unset **(Output 1)**  then whatever you put as *word* ```Friend``` substitutes *parameter* ```$yourname```
If *value* is typed ```Dennis``` then *parameter* ```$yourname``` is replaced with it **(Output 2)**


## :=

Similar to **:-** except it *assigns* value  to *parameter* as well and not just expand.  

**Example:**

**Input Script:**

```
#!/bin/bash
# This will be a comparison between :- and :=
# Name will be called paraexpan2.bash
A=''
B=''
echo ${A:=Test with Equal}
echo ${B:-Test with Minus}
echo 1. $A
echo 2. $B

```

**Command Line:**

```
./paraexpan2.bash

```

**Output:**

```
Test with Equal
Test with Minus
1. Test with Equal
2.

```
As you can see the test with :- was not *assigned*

## :?

If parameter is null or unset, the expansion of word (or a message to that effect if word is not present) is written to the standard error and the shell, if it is not interactive, exits. Otherwise, the value of parameter is substituted.
This is similar to *:=* but it just displays an error if *parameter* is unset or nulled.

**Example:**
**Input Script:**

```
#!/bin/bash
# This will show an example of :?
# The filename will be paraexpan3.bash

echo What is your name?
read yourname
echo "Your name is: ${yourname:?ERROR}"

```

**Command Line:**

```
./paraexpan3.bash

```


**Output 1:**

```

What is your name?
Dennis
Your name is: Dennis

```

**Output 2:**

```

What is your name?

./ paraexpan3.bash: line 7: yourname: ERROR

```

## :+

If parameter is null or unset, nothing is substituted, otherwise the expansion of word is substituted.

**Example:**

**Input Script:**

```
#!/bin/bash
# This will show an example of :+
# The filename will be paraexpan4.bash

echo What is your name?
read yourname
echo ${yourname:+YOU HAVE NO NAME}"

```


**Command Line:**

```
./paraexpan4.bash

```


**Output 1:**


```
What is your name?
Dennis
YOU HAVE NO NAME

```

**Output 2:**


```
What is your name?



[root@localhost scripts]#

```
So looking back at the definition if *parameter* is null or unset, nothing is substituted or in this case its replaced with blank space. Otherwise the *expansion word* ```Dennis``` is substituted with ```YOU HAVE NO NAME```.







[< Back: echo & printf](https://sxcdennis.github.io/basic-shell-scripting/echo%20%26%20printf "echo & printf")
| [Next: Loops >](https://sxcdennis.github.io/basic-shell-scripting/Loops "Loops")

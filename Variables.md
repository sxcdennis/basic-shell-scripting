# Variables
In this section we'll talk about variables and how to define them. There are also input/output scripts to go over.
A variable is memory to where we can assign value, and manipulate its contents.


# Video:

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
Also notice that there are double quotes**""** between commands. This is because without the quotes the arguments for the command would run differently.<br>
For example lets say you run the command ```#touch my file.file``` you would create **two** files: my and file.file vs ```#touch "my file.file"``` which would create **one** file: my file.file

## Special Variables
There are a set of variables that are already set for you already. They cannot have values assigned to them. <br>
The first set of variables are numbers. **$0** ,**$1 - $9**, and **$#**. All of them having different functionalities. <br>
**$0:** Is the basename of the program that is called. Example: Your script name is **test1.sh** located in ```/home/scripts```, if you call the variable it would output ```/home/scripts/test1.sh```<br>
**$1-$9:** These are whatever **named** parameters to which the script was called with.
For example lets say I have a script named testpara1.sh :
```
#!/bin/bash
echo "My First parameter is $1"
echo "My Second parameter is $2"
```
Now if you call the script without stating the parameters it would output:
**Output:**<br>
```
My First parameter is
My Second parameter is
```
Now try running the script with parameters. For example: ./testpara1.sh Onepara TwoPara
**Output:**<br>
```
My First parameter is Onepara
My Second parameter is TwoPara
```

[< Back: Running Simple Tasks](https://sxcdennis.github.io/basic-shell-scripting/Running%20Simple%20Tasks "Running Simple Tasks")
| [Next: If then Statements >](https://sxcdennis.github.io/basic-shell-scripting/If%20then%20Statements "If then Statements")

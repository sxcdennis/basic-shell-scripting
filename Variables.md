# Variables
In this section we'll talk about variables - how to define them, Input/Output variables, and Special Variables.
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
Also notice that there are double quotes **""** between commands. This is because without the quotes the arguments for the command would run differently.<br>
For example lets say you run the command ```#touch my file.file``` you would create **two** files: my and file.file vs ```#touch "my file.file"``` which would create **one** file: my file.file

## Special Variables
There are a set of variables that are already set for you already. They cannot have values assigned to them. The following is a table with all of the special variables. I urge you to practice them on your own. I will not go into detail with all of them, but I will go over a few of them.
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
      <td><b>Internal Field Separator</b>: The default value is <b>SPACE</b>, <b>TAB</b> and a <b>NEWLINE</b>. You can change this to whatever you want. </td>
      </tr>
      <tr>
      <td>$* </td>
      <td> All parameters stated on command ("$1" "$2" "$3" "$4" etc…). The values are separated by the first character in $IFS. Does not preserve quoting and whitespaces.</td>
      </tr>
      <tr>
      <td> $$</td>
      <td>Process number of current running shell.</td>
      </tr>
      <tr>
      <td> $!</td>
      <td>Number of last background process.</td>
      </tr>
      <tr>
      <td>#?</td>
      <td>Exit value of last executed command.</td>
      </tr>
      <tr>
      <td>$-</td>
      <td>Prints current options/flags in current shell or those set by user (Examples: -i, -h).</td>
      </tr>
      <tr>
      <td> $_ </td>
      <td> In a script, it will execute previous command argument.</td>
      </tr>
    </tr>
  </tbody>
</table>
<br>


**$0:** Will produce the pathname along with the filename. Example: Your script name is **test1.sh** located in ```/home/scripts```, if you call the variable it would output ```/home/scripts/test1.sh```
<br>

**$1-$9:** These are whatever **named** parameters to which the script was called with.
For example lets say I have a script named testpara1.sh :
```
#!/bin/bash
echo "My First parameter is $1"
echo "My Second parameter is $2"
```
Now if you call the script without stating the parameters it would output:
**Output:**
<br>
```
My First parameter is
My Second parameter is
```
Now try running the script with parameters. For example: ```./testpara1.sh Onepara TwoPara```
**Output:**
<br>

```
My First parameter is Onepara
My Second parameter is TwoPara
```
**$#:** Displays the number of parameters. For example



[< Back: Running Simple Tasks](https://sxcdennis.github.io/basic-shell-scripting/Running%20Simple%20Tasks "Running Simple Tasks")
| [Next: If then Statements >](https://sxcdennis.github.io/basic-shell-scripting/If%20then%20Statements "If then Statements")

# Exit Codes
Every command returns an exit code.
Exit codes are a number between 0 and 255.
A successful command returns a 0, while unsuccessful ones return non-zero. This was briefly discussed in the  [variables section](https://sxcdennis.github.io/basic-shell-scripting/Variables "Variables") .

# Video:


# $? and exit
 We can use either **exit** or **$?** to show exit status.

 **Example**

 ```
#!/bin/bash
# Example of exit status
# name this exit1.sh

echo "hello"
echo Exit status number: $?

echi "hello"
echo Exit status number: $?

#This will return a status if file exists.
ls /home/scripts/text.txt
if [ $? -eq 0 ]
then
echo "File exists"
else
echo "File does not exist"
fi

# We can use ! to do the opposite

! bogus_command
echo "Last Exit Code Reversed: $?"

exit
 ```

 **Output**

 ```

hello
Exit status number: 0
./exit.sh: line 7 echi: command not found
Exit Status number: 127
ls: cannot access /home/scripts/text.txt: No such file or directory
File does not exist
./exit.sh: line 21 bogus_command: command not found
Last Exit Code Reversed: 0

 ```
As you can see, you can manipulate all the codes to do certain things.

**Example 2**

```

#!/bin/bash
# This is the 2nd example of using exit.
# We'll name is exit2.sh
# You can exit by using a specific number.
# To verify this type "echo $?" after script terminates.

echo hello  
exit 12

```

**Output**

```

hello
[root@localhost scripts]#echo $?
12

```

[< Back: Case Statements](https://sxcdennis.github.io/basic-shell-scripting/Case%20Statements "Case Statements") || [Next: Functions >](https://sxcdennis.github.io/basic-shell-scripting/Functions "Functions")

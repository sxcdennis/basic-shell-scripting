# Functions:

Functions are a great way to reuse code. They are codes where you can call multiplies times within a script( or even other script files ).

# Video:

https://youtu.be/I1cthkuMS7s

# Syntax

There are two ways functions can be formatted.

**Option 1:**

```

function_name () {
  < commands >
}

```

**Option 2:**

```

function function_name {
  < commands >
}

```
**Notes:**

1. Either one of the above options are the same. In other programming languages it is common to have arguments passed inside the brackets *()*. In Bash they are just there for decoration.

2. The function must be defined before they are called.

**Example 1**

```

#!/bin/bash
# An example of a function
# We'll name this function1.sh

use_echo () {
  echo "Hello I am a function"
}

use_echo
use_echo

```


**Output**

```

Hello I am a function
Hello I am a function

```


**Example 2**

```

#!/bin/bash
# An example of a function
# We'll name this function2.sh

if [ "$USER" = root ]
then
  function root_greet {
    echo "Hello root"
  }
  else
  echo "You are not root!"
  fi

root_greet #This will work for root only other users will get an error


```

**Output 1**

```

Hello root

```

**Output 2**

```
You are not root!
./function2.sh: line 14 root_greet: command not found

```

**Example 3:**

```

#!/bin/bash
# An example of functions
# We'll call this function3.sh

add_user ()
{
  user=$1
  pass=$2
  shift; shift;
  comm=$@
  echo "Currently adding user: $user"
  echo useradd  -c "$comm" $user
  echo passwd $user $pass
  echo "Successfully added user: $user ($comm) with password $pass"
  echo
}


# Main script starts here
add_user bob 123abc This is a really bad pw
add_user joe cba321 This is not that great of a password either
echo "End"

```

**Output**

```

Currently adding user: bob
useradd -c This is a really bad pw bob
passwd bob 123abc
Successfully added user: bob (This is a really bad pw) with password 123abc

Currently adding user: joe
useradd -c This is not that great of a password either joe
passwd joe cba321
Successfully added user: joe (This is not that great of a password either ) with password bca321
End

```

## Variable Scopes
A scope refers to which part of a script can see what variables. By default, variables are **global**. That means they are they are visible anywhere in the script. We can also create **local** variables so they are only visible within the function.

```
local variable_name=< variable_value >

```

It is best practice to use local variables to keep everything contained. This way it is better to not have accidents within the script by possibly having the same variable name.

**Example**

```

#!/bin/bash
# This shows the difference between local and global variables
# named localvar.sh

var_change (){
  local a="local 1"
  local b="local 2"
  echo "Inside function: var1 is $a and var2 is $b"
  var1="changed again"
  var2="2 changed again"
}

 a="global 1"
 b="global 2"
 echo
 echo "Before function is called: var1 is $a and var2 is $b"
 echo
 var_change
 echo
 echo "After function is called: var1 is $a and var2 is $b"


```

**Output**

```

Before function is called: var1 is global 1 and var 2 is global 2

Inside function: var1 is local 1 and var2 is local 2

After function is called: var1 is global 1 and var2 is global 2


```

As you can tell from the previous example, local variables are all within the function. This also helps with not getting mixed up with variables that are outside of the script.

## Overriding commands
It's possible to have a function name that you would normally use as command lines.
For example, lets say every time you call the **ls** command you want it to use **ls -ld**

**Example:**
```
#!/bin/bash
# Overriding commands using ls
# Name this orcs.sh

ls () {
  command ls -ld
}

ls

```

# Libraries

It's common practice to have library files where you can call functions within the library. Libraries are basically a file full of function(s) that you can call from a different script.

 **Example**

 Lets say you have a library called **first.lib**

```
# first.lib
# Note there's no #! /bin/bash

#Print users details
userdetails() {
        oldifs="$IFS"
        IFS=:            
        read -p "Enter a user name to be searched:" uname
        echo ""
        read -r username pass uid gid comments homedir shell <<< "$(cat /etc/passwd | grep   "^$uname")"
        echo "Username is: $username"
        echo "User's ID: $uid"
        echo "User's GID: $gid"
        echo "User's Comments: $comments"
        echo "User's Home Directory: $homedir"
        echo "User's Shell: $shell"
        echo
        IFS="$oldifs"        
}

```

Now you want to call this library using a script.
There are two ways you can call Libraries

```
. /path/to/library

OR

source /path/to/library

```

**Example:**

```

#!/bin/bash
# This is an example of using library
# name is calllib.sh

source /home/scripts/first.lib

#calling function from library

userdetails


```

**Output**

```
Enter a username to be searched: root

Username is: root
User's ID: 0
User's GID: 0
User's Comment: root
User's Home Directory: /root
User's Shell: /bin/bash

```

[< Back: Exit Codes](https://sxcdennis.github.io/basic-shell-scripting/Exit%20codes "Exit Codes")  || [Next: Arrays >](https://sxcdennis.github.io/basic-shell-scripting/Arrays "Arrays")

# Arrays
Array is a variable which contains multiple values that may be of same type or of a different type. There are two types of arrays **indexed** array and **associative** arrays. *Associative* arrays can be defined using **-A** while *indexed* are created by using **-a**.  Array index starts with zero. In this section we'll talk about: **Creating, Adding, Deleting Arrays and Operations**

# Video

https://youtu.be/LJ_S1bKMpmc

# Creating Arrays
We can create an array by using several different ways.

**1. Using declare command**

**Syntax:**

```
declare -a my_array

or

declare -A my_array

```

**Example:**

```

declare -a myfiles

or

delcare -A myfiles

```

**2. Indirect Declaring**

**Syntax**

```

Array_Name[index]=value

```
**Example:**

```

NAME[0]="Happy"
NAME[1]="Unhappy"
NAME[2]="Sad"
NAME[3]="Joyful"
NAME[4]="Jolly"


```

**3. Compound Assignment**

**Syntax**

```

Array_Name=(value1 value2 value3 ... value*)

or

Array_Name=([Index_Number1]=String1 [Index_Number2]=String2 [Index_Number3]=String3 [Index_Number*]=String*)

```

**Example**

```
Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

or

Array_Name=([1]=10 [2]=20 [3]=30)

```


# Array Operations

Now that you know how to create arrays, we can figure out how to make use of them in different ways.

## Print all values of an array

**Syntax**

```

${array_name[@]}

or

${array_name[*]}

```


**Example**

```

#!/bin/bash
# This w ill show how to print all values of an array
# We'll name this arrays1.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

echo "${Unix[*]}"
echo "${Unix[@]}"


```

**Output**

```

Debian Red Hat Ubuntu Fedora CentOS FreeBSD
Debian Red Hat Ubuntu Fedora CentOS FreeBSD

```
## Print specific values of an array

**Syntax**

```

${array_name[value_number]}

```


**Example**

```

#!/bin/bash
# This will print a specific value of an array
# We'll name this arrays2.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

echo "${Unix[0]}"
echo "${Unix[1]}"
echo "${Unix[2]}"

```

**Output**

```

Debian
Red Hat
Ubuntu


```
## Print range values

**Syntax**

```

${array_name[*]:range}

or

${array_name[*]}

```


**Example**

```

#!/bin/bash
# This will print a range of the array values  
# We'll name this arrays3.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

echo "${Unix[@]:0}"
echo "${Unix[*]:1}"
echo "${Unix[@]:2}"
echo "${Unix[@]:3}"
echo "${Unix[*]:4}"
echo "${Unix[@]:5}"
echo "${Unix[@]:6}"
echo
echo "${Unix[@]:0:1}"
echo "${Unix[*]:0:2}"
echo "${Unix[@]:0:3}"
echo "${Unix[@]:0:4}"
echo "${Unix[*]:0:5}"
echo "${Unix[@]:0:6}"
echo
echo "${Unix[@]:0:1}"
echo "${Unix[*]:1:2}"
echo "${Unix[@]:2:3}"
echo "${Unix[@]:3:4}"
echo "${Unix[*]:4:5}"
echo "${Unix[@]:5:6}"

```

**Output**

```

Debian Red Hat Ubuntu Fedora CentOS FreeBSD
Red Hat Ubuntu Fedora CentOS FreeBSD
Ubuntu Fedora CentOS FreeBSD
Fedora CentOS FreeBSD
CentOS FreeBSD
FreeBSD

Debian
Debian Red Hat
Debian Red Hat Ubuntu
Debian Red Hat Ubuntu Fedora
Debian Red Hat Ubuntu Fedodra CentOS
Debian Red Hat Ubuntu Fedora CentOS FreeBSD

Debian
Red Hat Ubuntu
Fedora CentOS FreeBSD
CentOS FreeBSD
FreeBSD



```


## Get the size of an array

To get the size of a particular array, use the **#**(hash) sign to print the length.

**Syntax**

```

echo ${#array_name[@]}

or

echo ${#array_name[*]}

or

echo ${#array_name}

```


**Example**

```

#!/bin/bash
# This will print the array size
# We'll name this arrays4.sh

declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")
echo ${#Unix[@]}
echo ${#Unix[*]}
echo ${#Unix}

```

**Output**

```

6
6
6

```


## Search and replace value


**Syntax**

```

${array_name[@]/value_name/new_value_name}

or

${array_name[*]/value_name/new_value_name}

```


**Example**

```

#!/bin/bash
# This will search for an array value and replace it
# We'll name this arrays5.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")
echo ${Unix[@]/CentOS/Arch Linux}
echo ${Unix[*]/Ubuntu/Peppermint}
```

**Output**

```

Debian Red Hat Ubuntu Fedora Arc Linux FreeBSD
Debian Red Hat Peppermint Fedora CentOS FreeBSD


```

## Add new value to existing array


**Syntax**

```

array_name=(${array_name[@]} "value1" value2" "value3" "value*")

or

array_name=(${array_name[*]} "value1" value2" "value3" "value*")


```


**Example**

```

#!/bin/bash
# This adds new values to exisitng array
# We'll name this arrays6.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

Unix=(${Unix[@]} "value1" "value2" "value3" "value4")

echo ${Unix[7]}
echo ${Unix[8]}
echo ${Unix[9]}
echo ${Unix[10]}
echo ${Unix[@]}

```

**Output**

```

value1
value2
value3
value4
Debian Red Hat Ubuntu Fedora CentOS FreeBSD value1 value2 value3 value4


```

## Remove a value of an array


**Syntax**

```

unset Array_Name[value_number]

```


**Example**

```

#!/bin/bash
# This remove values of a certain array
# We'll name this arrays7.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

echo ${Unix[@]}

unset Unix[0]
echo ${Unix[@]}

unset Unix[1]
echo ${Unix[@]}

unset Unix[2]
echo ${Unix[@]}

unset Unix[3]
echo ${Unix[@]}

```

**Output**

```

Debian Red Hat Ubuntu Fedora CentOS FreeBSD
Red Hat Ubuntu Fedora CentOS FreeBSD
Ubuntu Fedora CentOS FreeBSD
Fedora CentOS FreeBSD
CentOS FreeBSD

```

## Deleting Arrays

**Syntax**

```

unset Array_Name

```


**Example**

```

#!/bin/bash
# This deletes contents of an array
# We'll name this arrays10.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

unset Unix
echo ${Unix[@]}
echo ${#Unix[@]}

```

**Output**

```


0

```

## Copy an array


**Syntax**

```

New_arrayName=(${array_name[@]})


```


**Example**

```

#!/bin/bash
# This will copy an array
# We'll name this arrays8.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")

Linux=(${Unix[@]})
echo ${Linux[@]}

```

**Output**

```

Debian Red Hat Ubuntu Fedora CentOS FreeBSD


```

## Combining arrays

**Syntax**

```

New_arrayName=( "${array_name1[@]}" "${array_name2[@]}" "${array_name3[@]}" "${array_name*[@]}")

```


**Example**

```

#!/bin/bash
# This will combine arrays
# We'll name this arrays9.sh
declare -a Unix=( "Debian" "Red Hat" "Ubuntu" "Fedora" "CentOS" "FreeBSD")
declare -a Shell=( "bash" "ksh" "jsh" "rsh" )
NixShell=("${Unix[@]}" "${Shell[@]}")

echo ${NixShell[@]}

```

**Output**

```

Debian Red Hat Ubuntu Fedora CentOS FreeBSD bash ksh jsh rsh


```

## Load Content of a File into an array

**Syntax**

```

declare -a array_name=( `cat "filename" `)

echo ${arrayname[@]}


```


**Example**

```

#!/bin/bash
echo this will be a good script > filename.txt

declare -a newname=( `cat "filename.txt" ` )

echo ${newname[@]}

rm filename.txt

```

**Output**

```

This will be a good script


```

|| [< Back: Functions](https://sxcdennis.github.io/basic-shell-scripting/Functions "Functions")

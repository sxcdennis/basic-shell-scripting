# Arrays
Array is a variable which contains multiple values that may be of same type or of a different type. There are two types of arrays **indexed** array and **associative** arrays. *Associative* arrays can be defined using **-A** while *indexed* are created by using **-a**.  Array index starts with zero. In this section we'll talk about: **Creating, Operations, Adding, & Deleting Arrays**

# Videos


# Creating Arrays
We can create an array by using several different ways.

1. Using declare command
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

2. Indirect Declaring

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

3. Compound Assignment

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

## Print values of an array




## Print keys  of an array



## Get the size of an array


## Get offset and size of array



## Get offset and size of element of array


## Search and replace elements


## Copying an array


## Expanding two arrays to one


## Load file into an array


# Adding Array Elements

# Deleting Arrays


## Delete Entire Array

## Delete an element from an array


|| [< Back: Functions](https://sxcdennis.github.io/basic-shell-scripting/Functions "Functions")

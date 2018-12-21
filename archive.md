#Archive stuff
These are some materials I decided not to put in..
They wont be in any particular order so if you stumble upon this information you can try to decipher it yourself :P

<table>
  <thead>
    <tr>
      <th>Variable</th>
      <th>Function</th>
    </tr>
  </thead>
  <tbody>
<tr>
<td> $_ </td>
<td> In a script, it will execute previous character argument.</td>
</tr>
</tr>
</tbody>
</table>
<br>
## $_ :

In a script, it will execute previous character argument.

**Example:**

**Input Script:**

```

#!/bin/bash
# This will be an example of using $_
# The filename will be called lastchar.bash

echo Hello what is your name?
read a

echo Nice to meet you "$a!"

echo $_ What a wonderful name.

```

**Command Line:**

```
./lastchar.bash
```

**Output:**

```
Hello What is your name?
Stupid
Nice to meet you Stupid!
Stupid! What a wonderful name.

```



## File test operators

```
-b - True if file is a block special file
-c - True if file is a character special file
-d - True if file is a directory
-e - True if file exists
-f - True if file is a "regular file"
-g - True if file has SGID bit set
-h - True if file is a symbolic link
-L - True if file is a symbolic link
-p - True if file is a FIFO
-r - True if you have read access to file
-S - True if file is a a socket
-s - True if file size is greater than 0
-u - True if file has setuid flag set
-w - True if you have write access to file
-x - True if you have execute permissions to file

```

## String operators (Will work with integers but will treat them as strings)

```
= - True if left hand string is equal to right hand string
!= - True if left hand string is not equal to right hand string
-z - True if length of string is zero
-n - True if length of string is non-zero
string - True if string exists

```

## Relational operators (Will not work with strings)


```
-eq - True if left hand integer is equal to right hand integer
-ne - True if left hand integer is not equal to right hand integer
-gt - True if left hand integer is greater than right hand integer
-ge - True if left hand integer is greater than or equal to right hand integer
-lt - True if left hand integer is less than right hand integer
-le - True if left hand integer is less than or equal to right hand integer

```


## Boolean operators

```
! - True if expression is false
-o - True if either left hand expression or right hand expression are true
-a - True if both left hand expression and right hand expression are true
Arithmetic operators (Within shell arithmetic expansion or expr)

+ - Adds values on either side of the operator
- - Subtracts right hand integer from left hand integer
* - Multiplies values on either side of the operator
/ - Divides left hand integer from right hand integer
% - Divides left hand integer from right hand integer and returns remainder
= - Assigns right hand to left hand
== - True if both integers are equal
!= - True if both integers are not equal

```

## Other

```
-t - True if file descriptor is open and
associated with a terminal

```

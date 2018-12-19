#  echo & printf

In this section we'll talk about the use of echo and printf within bash scripting.

Most of the definitions were taken from the manual pages of each command.


# Video:


# echo

**echo** is probably one of the most used command for Linux bash. It inputs a line of text and displays it standard output.

I will not go over all of the options to them, but go over *some* of the common options.

I urge you to practice them on your own.

### echo syntax

```
**echo** [option] [string]

```

### Common Options

```
 -n
     Do not output the trailing newline.

 -e
     Enable interpretation of the following backslash-escaped
     characters in each String:


    \b          backspace

    \c          suppress trailing newline

    \e          escape

    \n          new line

    \r          carriage return

    \t          horizontal tab

    \v          vertical tab


```
### Examples of echo

## -n
This makes it so echo does *not* output a new line

**Command Line:**

```
echo -n Hello

```


**Output:**

```

Hello[root@localhost scripts]#


```
As you can see it ignores outputting a new line.

## -e with \b
This makes so there's no spaces in between characters


**Command Line:**

```
echo -e "Hello \bthere \bmy \bname \bis \bDennis"


```

**Output:**

```

HellotheremynameisDennis

```

## -e with \n

Treats each \n for new line

**Command Line:**

```

echo -e "Hello \nmy \nname \nis \nDennis"

```

**Output:**

```
Hello
my
name
is
Dennis

```
## -e with \t

Treats each \t as horizontal tabs

**Command Line:**

```

echo -e "Hello \tmy \tname \tis \tDennis"

```

**Output:**

```

Hello  my     name      is      Dennis

```
## -e with \v

**Command Line:**

```

echo -e "Hello \vmy \vname \vis \vDennis"

```

**Output:**

```

Hello
      my
          name
              is
                  Dennis
```

## -e with \c

**Command Line:**

```

echo -e "Hello my name is \cDennis"

```

**Output:**

```

Hello my name is [root@localhost scripts]#

```

## -e with \r

**Command Line:**

```

echo -e "Hello my name is \rDennis"

```

**Output:**

```

Dennisismy name is

```


# printf

printf prints a formatted string to standard output. It is a handy way to do more precise formatted outputs compared to echo.

I will not go over all of the options to them, but go over *some* of the common options.

I urge you to practice them on your own.

### printf syntax

```

**printf** FORMAT [ARGUMENT]

or
**printf** [OPTION]

```
*OPTIONS* Can be *FORMAT* or *ARGUMENT*

*FORMATS* control the output and defines the way *ARGUMENTS* are expressed

*ARGUMENTS* is inserted into formatted output.

###Common options

```

\b     backspace

\n     new line

\t     horizontal tab

%s     Character string char

```


## Examples of printf

# printf with %s

**Command Line:**

```
printf "Hello %s $LOGNAME"

```


**Output**

```

Hello root[root@localhost scripts]#


```

# printf with \n

**Command Line:**

```

printf "Hello \n $LOGNAME"


```


**Output**

```

Hello
root[root@localhost scripts]#

```

# printf with \b

**Command Line:**

```

printf "Hello\b $LOGNAME"

```


**Output**

```

HELL root[root@localhost scripts]#

```

# printf with \t

**Command Line:**

```

printf "HELLO\t $LOGNAME"


```


**Output**

```
HELLO   root[root@localhost scripts]#

```




[< Back: Running Simple Tasks](https://sxcdennis.github.io/basic-shell-scripting/Running%20Simple%20Tasks "Running Simple Tasks")
|[Next: Variables >](https://sxcdennis.github.io/basic-shell-scripting/Variables "Variables")

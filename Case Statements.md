# Case Statements

Sometimes you want to make different paths upon a variable matching in a series of patterns. Although you can do that with *if then statements*, **case** statements are much cleaner. We end each *case* statements with **esac** which is case backwards.

# Video:

https://www.youtube.com/watch?v=xkn-du1jhgc

## case statements

**Syntax**

```
case [ variable ] in
    pattern 1)
      [ commands ]
      ;;
    pattern 2)
      [ commands ]
      ;;
    pattern *)
        [ commands ]
        ;;
esac

```

**Example 1**

```

#!/bin/bash
# case example 1
# name it case1.sh

echo "Type start stop or restart"
read a
case $a in
  start)
    echo starting
    ;;
  stop)
    echo stopping
    ;;
  restart)
    echo restarting
    ;;
esac     

```

**Output**


```

Type start stop or restart
start
starting

stop
stopping

restart
restarting
```

**Example 2**

```

#!/bin/bash
# More harder example of case
# Name this case2.sh

space=$( df -h | awk '{ print $5 }' | sort -n | tail -n 1 | sed 's/%//' )

case $space in
  [1-5]*)
  echo "Plenty of disk space. You have used $space % disk space!"
  ;;
  [6-7]*)
  echo "There might be a problem in near future. You have used $space % disk space!"
  ;;
  8*)
  echo "Maybe we should clear out some old files. You have used $space % disk space!."
  ;;
  9*)
  echo "We could have some serious issues. You have used $space % disk space!"
  ;;
  esac

```

**Output**

```

Plenty of disk space. You have used 15% disk space!

```
**case** statements can be powerful tools as you can see from the above example.


[< Back: If then Statements](https://sxcdennis.github.io/basic-shell-scripting/If%20then%20Statements "If then Statements") || [Next: Exit Codes >](https://sxcdennis.github.io/basic-shell-scripting/Exit%20codes "Exit Codes")

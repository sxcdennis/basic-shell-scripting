# Scripting Standards 
# Video:
# Formatting:
It is essential that formatting is followed in scripting, otherwise it would be impossible to read or understand what people are thinking. Imagine having a large script file and having coding all over the place without any format. If someone new were to take over the script they would be extremely confused, or even if you were to take over someone else's script you would be too!

The first line of a UNIX/Linux tells that file to be executed. 
```
#!/bin/bash
```
This tells us that /bin/bash will be executed. There are several other types such as: /bin/sh, /bin/perl, & /bin/python, but we will be using /bin/bash throughout this whole guide.

The second line is usually started with a special symbol  <b>"#"</b> which will be our comments. This symbol: <b>"#"</b> is completely ignored by shell with the exception of the first line <b>"#!"</b>. Typically comments should include: Author, Date Created, Description of script, & Date Modified.

<b> Example: </b>
```
#!bin/bash
# Author: Dennis 
# Date Created: 12/12/2018
# Description: This is a script 
# Date Modified: 12/13/2018 
```

The following lines typically are followed by [Variables](https://github.com/sxcdennis/basic-shell-scripting/blob/master/Variables.md "Variables") which are covered later in the guide.

Next are <b> commands</b> such as: echo, cp, grep etc..

Next are followed by <b> statements</b>: if, while, for etc..

<b>An Example of a well formated script:</b>
```
#!bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This is a script 
# Date Modified: 12/13/2018

a="My name is Dennis"

echo Hello $a

date 
mount -h

          if { $a -eq file }
          then echo this 
          else
          echo that
          fi
```

[ < Back: Introduction ](https://github.com/sxcdennis/basic-shell-scripting/blob/master/README.md) | [ Next: The First Script >](https://github.com/sxcdennis/basic-shell-scripting/blob/master/The%20First%20Script.md "The First Script")

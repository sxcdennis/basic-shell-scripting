# Scripting Standards
In this section we'll go over the following: Naming Conventions, Formatting, File Permissions & Execution , and Sequence of scripts.

# Video:

# Naming Conventions

Typically people have a directory for all of their personal scripts. **Example:** I would put my scripts under ```/home/scripts```
The script should have an extension followed by shell type. **Example:** ``` .sh, .bash, .perl, .python ```
The script name should describe the script in some way.  **Example:** If you had a script that checks the date and uptime, maybe you'd name the file datenuptime.sh


# Formatting:
It is essential that formatting is followed in scripting, otherwise it would be impossible to read or understand what people are thinking. Imagine having a large script file and having coding all over the place without any format. If someone new were to take over the script they would be extremely confused, or even if you were to take over someone else's script you would be too!

The first line of a UNIX/Linux tells that file to be executed.
```
#!/bin/bash
```
This tells us that /bin/bash will be executed. There are several other types such as: /bin/sh, /bin/perl, & /bin/python, but we will be using /bin/bash throughout this whole guide.

The second line is usually started with a special symbol  **"#"** which will be our comments. This symbol: **"#"** is completely ignored by shell with the exception of the first line **"#!"**. Typically comments should include: Author, Date Created, Description of script, & Date Modified.

**Example:**
```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This is a script
# Date Modified: 12/13/2018
```

The following lines typically are followed by [Variables](https://sxcdennis.github.io/basic-shell-scripting/Variables "Variables") which are covered later in the guide.

Next are **commands** such as: echo, cp, grep etc..

Next are followed by **statements:** if, while, for etc..

**An Example of a well formated script:**
```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This is a script
# Date Modified: 12/13/2018

a="My name is Dennis"
count="100"
echo Hello $a

date
mount -h | grep else

if [ $count -eq 50 ]
then
echo Count is 50
else
echo Count is not 50
fi

```

# File Permissions & Execution
All scripts must be able to read & execute by whomever needs to execute the script.
To change permissions: ```#chmod a+rx script-name``` **or** ```#chmod 755 script-name```

To execute the script:   ```/filepath/file-name``` **or if you are in the directory of script file** ``` ./file-name```

# Sequence of scripts
Scripts are in a sequence of order read from top to bottom.
If I had the following script:
```
# !/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This is a script
# Date Modified: 12/13/2018
cd /home/
ll
echo Hello
```

This script will use the commands in the following order: <br>
**1st:** cd /home/ <br>
**2nd:** ll <br>
**3rd:** echo Hello <br>



[ < Back: Introduction ](https://sxcdennis.github.io/basic-shell-scripting/) || [ Next: The First Script >](https://sxcdennis.github.io/basic-shell-scripting/The%20First%20Script "The First Script")

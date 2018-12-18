# Running Simple Tasks
These are just some simple tasks scripts that use random commands

# Video:

# Basic Tasks
Create a new file named basicscripts1.bash
The following is an example of basic tasks script:

```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This is a script that performs basic tasks
# Date Modified: 12/13/2018
pwd
echo
ll
echo
whoami
echo
date
echo
cal
echo
cat c
echo
echo End of Script
```

Notice how every command is performed in a sequence read top to bottom like previously stated in Scripting Standards

# Basic Admin Tasks

The following are a few random scripts that perform administrative tasks.

**Example 1: This script performs some basic administrative tasks** <br>
```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This is a script that performs basic administrative tasks
# Date Modified: 12/13/2018
echo Running . . .
echo
top | head -5
echo
df -h
echo
uptime
```

**Example 2:  This script finds host name and username** <br>
```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This script finds host name and username
# Date Modified: 12/13/2018
echo Running . . .
echo
hostname
echo
whoami
```
**Example 3: This script tells username the date and how many people are logged in.**
```
#!/bin/bash
# Author: Dennis
# Date Created: 12/12/2018
# Description: This script tells username the date and how many people are logged in.
# Date Modified: 12/13/2018
echo "Hello `whoami`"
echo
echo "Today is `date`"
echo
echo "Number of user(s) logged in: `who | wc -l `"
echo
```
These are just some examples of basic tasks that can be ran into scripts. There will be a bit more complexity and functionalities later in the guide.
<br>
Keep reading!<br>
[ < Back: The First Script ](https://sxcdennis.github.io/basic-shell-scripting/The%20First%20Script) | [ Next: Variables >](https://sxcdennis.github.io/basic-shell-scripting/Variables "Variables")

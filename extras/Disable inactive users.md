# Disable inactive users

This script will disable accounts with the name test that have not been used for 90 days.


# Video
https://youtu.be/VyRQgnI901k


## Code

**disableoldusers.sh**

```
#!/bin/bash
lastlog -b 90 | grep "test" | awk '{print $1}' | xargs -I {} usermod -L {}

```

To check to see if accounts are disabled use command :

```
grep test /etc/shadow

```
If there's an *!* in front of each user-name, then that means they are disabled.

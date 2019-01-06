# List user login status

The following is an interactive script that will list users for specific dates.

# Video

## Code

```

#!/bin/bash

echo "Please enter a month (Ex: Jan Feb Mar)"
read a
echo
echo "Please enter date (Ex: 10 11 12 13)"
read b
echo
last | grep "$a $b"  | awk '{print $1}'


```


## Output

```

Please enter month (Ex: Jan Feb Mar)
Dec

Please enter date (Ex: 10 11 12 13)
10

root
reboot
root
reboot

```

## Summary

Overall this script is useful for listing users for specific dates. If you want to list users that are logged in currently, you can use the command `who`

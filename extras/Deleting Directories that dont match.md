# Deleting Directories that don't match

Sometimes there are directories that are in /home but don't belong there because they aren't directories that match /etc/passwd ( file that lists users ). The following script will
match users from /etc/passwd and display which directories do not belong.


# Video


## Code

```
#!/bin/bash

for DIR in /home/*
do
check=$( grep -c "$DIR" "/etc/passwd" )
if [ $check -ge 1 ]
then
echo "Directory ($DIR) has a user assigned to it."
else
echo "Directory ($DIR) does NOT have a user assigned to it."
fi
done


```


## Output

```

Directory (/home/recycle) does NOT have a user assigned to it.
Directory (/home/scripts) does NOT have a user assigned to it.
Directory (/home/scripts2) does NOT have a user assigned to it.
Directory (/home/unknown) has a user assigned to it.

```

## Summary

Overall this script is useful to check to see any security issues. Perhaps someone created a directory that you did not expect to be there or someone left the company but their directory still exists there. You may want to delete the directory.

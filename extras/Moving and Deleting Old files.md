# Moving and Deleting Old files

It is essential to delete old files to keep clear up disk space. In this example, we're going to create a directory called *recycle* and create a script that moves all files from /home/scripts that are 10+ days old there. Follow up by creating a script that empties the recycle directory with a prompt.   

# Video

https://youtu.be/ixt6I6WBb5c

## Code


**moverecycle.sh**

```

#!/bin/bash
find /home/scripts/ -mtime +10 -exec mv -t /home/recycle/ {} \;

ls /home/recycle # this is to check if they were moved not really necessary though.

```


**empty_recycle.sh**

```

#!/bin/bash
rm -i /home/recycle/*

```

## Example Output

```

rm: remove regular file '/home/recycle/Helloworld1.bash' ? y
rm: remove regular file '/home/recycle/Helloworld2.bash' ? y
rm: remove regular file '/home/recycle/test2.sh' ? y
rm: remove regular file '/home/recycle/test.sh' ?  y

```

## Summary

These scripts can be put into one, but this was just an example of what can be done.

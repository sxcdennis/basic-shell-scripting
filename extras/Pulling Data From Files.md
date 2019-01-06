# Pulling Data from files

There are several ways to pull data from files but in this section, we'll go over some of the more common and efficient ways of doing so.

# Video

# Log files
There are several log files, but we'll only go over one of them: ```/var/log/messages ```

**Log Files**

```
/var/log/messages
/var/log/auth.log
/var/log/secure
/var/log/boot.log
/var/log/dmesg
/var/log/kern.log
/var/log/faillog
/var/log/cron
/var/log/yum.log
/var/log/maillog
/var/log/httpd/
/var/log/mysql.log

 ```


## Code

 ```
#!/bin/bash
# Author: Dennis
# Date: 12/12/18

grep -i error /var/log/messages > /home/scripts/errormessages.txt
cat /home/scripts/errormessages.txt


 ```


## Output

 ```




 ```

## Summary

 Since the output was nothing, that means no errors have occurred, but if there were errors it would show.

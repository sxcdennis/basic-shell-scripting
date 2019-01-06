# Central Logging

Sometimes you want to show all the error messages into one file. The following script is a great way to do that.

# Video

https://youtu.be/b1P1jc6lvQg


First you want to create the directory ```#mkdir /home/errors/```

## Code

**filtermsg.sh**

```
#!/bin/bash

tail -fn0 /var/log/messages | while read line
do
echo $line | grep -Ei "refused|invalid|fail|lost|shut|down|offline|error"
if [ $? = 0 ]
then
echo $line >> /home/errors/filtered_messages.txt
fi
done


```

So next we need to test it and maybe put some error messages into the system.

To put some errors we use the command ```logger -t ```  

**Example:** ```logger -t fail "Dennis is testing messages" ```

Next we want to run the script continuously in the background by using  the command *nohup*

For example: ```#nohup /home/scripts/filtermsg.sh &```


Finally, to display the messages use *cat* : ```#cat /home/errors/filtered_messages.txt```

## Output

```

Dec 12 13:01:02 localhost fail: Dennis is testing messages

```

Lets say you want to email this file to admins every time an error pops up. We can do that by creating a script as well.

**Example:**

```
#!/bin/bash

admins="admin1@example.com,admin2@example.com,admin3@example.com"
if [ -s /home/errors/filtered_messages.txt ]
then
cat /home/errors/filtered_messages.txt | mail -s "Filtered Messages from /var/log/messages" $admins
rm /home/errors/filtered_messages.txt
else
fi


```
Then finally you can just set this script to a cronjob.

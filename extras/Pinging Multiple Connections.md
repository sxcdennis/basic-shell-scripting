# Pinging Multiple Connections
Sometimes you may want to ping multiple connections. In this case we can make a script to tell you if the output is reachable or not without showing other data.

# Video

## Code

```

#!/bin/bash
# Author: Dennis
# Date: 12/12/18
# This will ping multiple ips and see if they are reachable

ip1=192.168.101.240
ip2=200.200.200.200
ip3=192.168.101.250

ping -c 1 $ip1  &> /dev/null
if [ $? -eq 0 ]
then
echo $ip1 is reachable
else
echo $ip1 is not reachable
fi

ping -c 1 $ip2  &> /dev/null
if [ $? -eq 0 ]
then
echo $ip2 is reachable
else
echo $ip2 is not reachable
fi

ping -c 1 $ip3  &> /dev/null
if [ $? -eq 0 ]
then
echo $ip3 is reachable
else
echo $ip3 is not reachable
fi

```


## Output

```

192.168.101.240 is reachable
200.200.200.200 is not reachable
192.168.101.250 is reachable

```

## Summary

As you can see this script tells us if the ip is reachable or not. You can also do this by calling ips from a different file or any other things you can think of.

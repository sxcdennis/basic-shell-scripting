# Interactive User Creation

The following script is a script to add users while checking if the UID and User exists or not using functions and loops.

# Video

https://youtu.be/FAVMgwoweI8

## Code

**createuser.sh**


```

#!/bin/bash

adduser()
{
  echo "Please enter a username."
  read -r u
  echo
  grep -q "$u" /etc/passwd
  if [ $? -eq 0 ]
  then
  echo
  echo "ERROR - User $u already exists."
  echo "Please choose another username."
  echo
  adduser
  else
  adduid
  fi
}

adduid()
{
  echo "Do you want to specify a user ID (y/n)? "
  read -r yon
  echo
  if [ "$yon" == y ]
  then
  echo "Please enter UID."
  read -r uid
  grep -q "$uid" /etc/passwd
  if [ $? -eq 0 ]
  then
  echo
  echo "ERROR -- UserID $uid already exists."
  echo "Please choose another  user ID"
  echo
  adduid
  else
  useradd "$u" -u "$uid"
  echo
  echo "$u account has been created."
  fi
  elif [ $yon == n ]
  then
  echo "User will be assigned a UID automatically."
  useradd "$u"
  echo
  echo "$u account has been created."
  fi
}
adduser


```

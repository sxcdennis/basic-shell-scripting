# Backup File in System
It is useful to backup systems by using *tar* and *gzip*.
In this seciton we'll go over a simple soultion that will backup the ```/home/scripts``` and ``/home/scripts2/`` directories into ``/home/backup`` directory.

# Video



## Code

```
#!/bin/bash 
tar cvf /home/backup/backup.tar /home/scripts/ /home/scripts2/
gzip /home/backup/backup.tar

```

Now after this was created you can check to see if the gzip was created by using the ls -l command. `` # ls -l /home/backup/ ``


## Output

```

-rw-r--r-- . 1 root root 1050105 DEC 12 15:32 backup.tar
-rw-r--r-- . 1 root root 550105 DEC 12 15:32 backup.tar.gz

```

## Summary

This was just an introduction to using tar and gzip to backup files. As you can see it is very powerful and can be used to create more complex scripts. For example, you can create a script that will send your compressed file to a remote system.

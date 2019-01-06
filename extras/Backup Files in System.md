# Backup Files in System

It is useful to backup systems by using *tar* and *gzip*.
In this section we'll go over a simple solution that will backup the ```/home/scripts``` and ``/home/scripts2/`` directories into ``/home/backup`` (create it) directory.

# Video

https://youtu.be/ylROFrX5QNQ


## Code

**backup.sh**

```
#!/bin/bash
tar cvf /home/backup/backup.tar /home/scripts/ /home/scripts2/
gzip /home/backup/backup.tar

```

Now after this was created you can check to see if the gzip was created by using the ls -l command. `` # ls -l /home/backup/ ``


## Output

```

-rw-r--r-- . 1 root root 14175 DEC 12 15:32 backup.tar.gz

```

## Summary

This was just an introduction to using tar and gzip to backup files. As you can see it is very powerful and can be used to create more complex scripts. For example, you can create a script that will send your compressed file to a remote system.

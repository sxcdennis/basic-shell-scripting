# Moving Files to remote hosts
Sometimes it's useful to copy files to multiple hosts, instead of copying them from one location to another you can do multiple at once.

## Code

```

for i in centos1 centos2 centos3 centos4

do
scp file $i:/tmp
done

```
